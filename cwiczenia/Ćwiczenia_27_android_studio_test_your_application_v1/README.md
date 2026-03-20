# Ćwiczenia 27 -- Android studio -- Testy

Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie MyTest na podstawie Empty Activity, dobierz
    odpowiednie API ( 28 -- Android 9).

1. Otwórz dokumentację:

    <https://developer.android.com/codelabs/advanced-android-kotlin-training-testing-basics#0>

    <https://developer.android.com/codelabs/advanced-android-kotlin-training-welcome#1>

    <https://developer.android.com/courses/kotlin-android-fundamentals/overview>

    <https://developer.android.com/codelabs/kotlin-android-training-internet-data?index=..%2F..android-kotlin-fundamentals#0>

1. Dodaj zależności dla JUnit 5

   Local Unit Tests. Testy jednostkowe uruchamiane na JVM
   – szybkie, nie wymagają emulatora.

   app/src/test/java  

   Instrumented Tests. Testy instrumentacyjne uruchamiane na urządzeniu/emulatorze,
   – np. testy UI Espresso

   app/src/androidTest/java

1. Użyj Ctrl+Shift+T będąc na nazwie klasy, aby wygenerować test.

1. Utwórz klasę:

   ```java
   public class RegistrationValidator {
       /**
        * Waliduje hasło: min 8 znaków, zawiera cyfrę.
        */
       public boolean isValidPassword(String password) {
           if (password == null) return false;
           return password.length() >= 8 && password.matches(".*\\d.*");
       }
   }
   ```

1. Utwórz klasę RegistrationValidatorTest.java :

   ```java
    import static org.junit.Assert.*;
    import org.junit.Before;
    import org.junit.Test;

    public class RegistrationValidatorTest {
        private RegistrationValidator validator;

        @Before
        public void setUp() {
            validator = new RegistrationValidator();
        }

        @Test
        public void isValidPassword_shortPassword_returnsFalse() {
            // Arrange (Przygotowanie)
            String pass = "1abc";
            
            // Act (Działanie)
            boolean result = validator.isValidPassword(pass);
            
            // Assert (Weryfikacja)
            assertFalse("Hasło zbyt krótkie powinno zostać odrzucone", result);
        }

        @Test
        public void isValidPassword_noDigit_returnsFalse() {
            assertFalse(validator.isValidPassword("abcdefghij"));
        }

        @Test
        public void isValidPassword_correctPassword_returnsTrue() {
            assertTrue(validator.isValidPassword("TajneHaslo123"));
        }
    }
   ```

1. Utwórz klasę LoginUiTest.java.

   Testujemy scenariusz:

   - użytkownik wpisuje błędne hasło -> klika przycisk -> widzi komunikat o błędzie.

   ```java
    @RunWith(AndroidJUnit4.class)
    public class LoginUiTest {
        @Rule
        public ActivityScenarioRule<MainActivity> activityRule =
                new ActivityScenarioRule<>(MainActivity.class);

        @Test
        public void loginError_isDisplayed_whenPasswordInvalid() {
            // Wpisz tekst
            onView(withId(R.id.password_field)).perform(typeText("123"), closeSoftKeyboard());
            
            // Kliknij przycisk
            onView(withId(R.id.login_button)).perform(click());

            // Sprawdź czy TextView wyświetla odpowiedni błąd
            onView(withId(R.id.error_message))
                    .check(matches(withText("Hasło jest zbyt krótkie")));
        }
    }
   ```

1. Architektura pod testy. Refaktoryzacja ćwiczeń 14.

  Aby przetestować logikę dodawania produktów, warto wydzielić ją z MainActivity
  do osobnej klasy (Separation of Concerns).

  Dzięki temu możemy napisać Unit Test bez uruchamiania emulatora.

1. Klasa: ProductManager.java (Logic)

   ```java
    public class ProductManager {
        private final List<Map<String, Object>> fruitsList = new ArrayList<>();

        public void addProduct(String name, String description, int imageResId) {
            if (name == null || name.isEmpty()) throw new IllegalArgumentException("Name cannot be empty");
            Map<String, Object> item = new HashMap<>();
            item.put("name", name);
            item.put("description", description);
            item.put("image", imageResId);
            fruitsList.add(item);
        }

        public int getCount() { return fruitsList.size(); }
        public List<Map<String, Object>> getList() { return fruitsList; }
    }
   ```

1. Zależności:

   ```xml
      dependencies {
        // Podstawowe biblioteki Android UI
        implementation(libs.appcompat)
        implementation(libs.material)
        implementation(libs.constraintlayout)

        // --- TESTOWANIE ---
        
        // Unit Testing (Local - uruchamiane na komputerze)
        testImplementation(libs.junit)

        // Instrumented Testing (Android - uruchamiane na emulatorze/telefonie)
        androidTestImplementation(libs.androidx.junit)
        androidTestImplementation(libs.androidx.espresso.core)
        
        // Opcjonalne: Espresso contrib (pomocne przy testowaniu ListView/RecyclerView)
        androidTestImplementation("androidx.test.espresso:espresso-contrib:3.6.1")

    }

   ```

1. Testy Jednostkowe (Unit Tests)

   Użyj skrótu Ctrl+Shift+T na nazwie klasy ProductManager,
   aby wygenerować test. Sprawdzamy sytuacje brzegowe
   (tzw. edge cases).

   ```java
    import org.junit.Test;
    import static org.junit.Assert.*;

    public class ProductManagerTest {
        
        @Test
        public void addProduct_validData_increasesSize() {
            ProductManager manager = new ProductManager();
            manager.addProduct("Jabłko", "Czerwone", 123);
            assertEquals(1, manager.getCount());
        }

        @Test(expected = IllegalArgumentException.class)
        public void addProduct_emptyName_throwsException() {
            ProductManager manager = new ProductManager();
            manager.addProduct("", "Opis", 123);
        }
    }
   ```

1. Testy UI (Instrumented Tests / Espresso)

   W kodzie mamy AlertDialog i FloatingActionButton.

   Testujemy pełny scenariusz użytkownika:

   ```text
   Kliknięcie FAB 

   -> Wpisanie danych 

   -> Potwierdzenie 

   -> Sprawdzenie czy element jest na liście.
   ```

1. MainActivityTest:

   ```java
    @RunWith(AndroidJUnit4.class)
    public class MainActivityTest {

        @Rule
        public ActivityScenarioRule<MainActivity> activityRule = 
                new ActivityScenarioRule<>(MainActivity.class);

        @Test
        public void testAddProductFlow() {
            // 1. Kliknij w FAB Add
            onView(withId(R.id.fabAdd)).perform(click());

            // 2. Wpisz dane w Dialogu
            onView(withId(R.id.editTextProductName)).perform(typeText("Nowy Produkt"));
            onView(withId(R.id.editTextProductDescription)).perform(typeText("Opis testowy"), closeSoftKeyboard());

            // 3. Kliknij "Dodaj" w AlertDialog
            onView(withText("Dodaj")).perform(click());

            // 4. Sprawdź, czy nowy element jest widoczny na liście
            onView(withText("Nowy Produkt")).check(matches(isDisplayed()));
        }

        @Test
        public void testDeleteProduct_showsToastWhenNoSelection() {
            // Kliknij usuń bez zaznaczenia
            onView(withId(R.id.fabDelete)).perform(click());
            
            // Sprawdź czy pojawił się Toast (wymaga customowego Matchera lub sprawdzania widoczności)
            onView(withText("Wybierz element do usunięcia"))
                .inRoot(withDecorView(not(is(activityRule.getScenario())))) // Specyficzne dla Toastów
                .check(matches(isDisplayed()));
        }
    }
   ```

1. Dodatkowe zadania

    - dopisz testy krawędziowe (null, puste stringi, znaki specjalne).
    - zaimplementuj RegistrationValidator z obsługą adresów e-mail (Regex)
    - dodaj nową aktywność
    - dodaj testy
  
1. KONIEC.
