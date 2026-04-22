# Ćwiczenia 15 -- Android studio -- BaseAdapter, Spinner

💡Na koniec zajęć prześlij pliki źródłowe (.xml, .java) + screeny do zasobu
w teams.

1. Utwórz projekt o nazwie ArrayAdapter na podstawie Empty Activity,
    dobierz odpowiednie API.

1. Otworzyć dokumentację:

   <https://developer.android.com/guide/topics/ui/controls/spinner>

   <https://developer.android.com/guide/topics/resources/string-resource#java>

   <https://developer.android.com/reference/android/widget/BaseAdapter>

1. Docelowo chcemy uzyskać :

   ![image1](media/image1.png)

   ![image2](media/image2.png)

1. Dodaj w activity_main.xml

   ![image3](media/image3.png)

1. W raw umieść plik z danymi:

   ![image4](media/image4.png)

1. Uzupełnij MainActivity.java:

   ![image5](media/image5.png)

1. Sprawdź czy poprawnie wczytujesz dane, np.:

   ![image6](media/image6.png)

1. Przetestuj aplikację, uruchom na urządzeniu.

   ![image7](media/image7.png)

1. Dodaj pliki png do drawable

   ![image8](media/image8.png)

1. Utwórz tablicę dla plików:

   ![image9](media/image9.png)

1. Dalej, szkielet dla onCreate():

   ![image10](media/image10.png)

1. Utwórz plik spinner_item.xml:

   ![image11](media/image11.png)

1. Utwórz klasę MyAdapter.java, rozrzesz ją o BaseAdapter:

   ![image12](media/image12.png)

1. Sprawdź czy posiadasz wbudowane metody:

   ![image13](media/image13.png)

1. Ostatnia metoda:

   ![image14](media/image14.png)

1. Wykonaj zadania:

   - dodaj obsługę kliknięcia w item, wyświetl toast

   ![image15](media/image15.png)

   ![image16](media/image16.png)

   ![image17](media/image17.png)

   - utwórz przycisk dodający nowy element do listy

   - zachowaj całą listę w ShredPreferences, sprawdź stan listy po
     rotacji urządzenia

   - przebuduj projekt tworząc klasę i listę, utwórz stosowny adapter

     ![image18](media/image18.png)

     ![image19](media/image19.png)

     ![image20](media/image20.png)

     Obsługa dla listenera:

     ![image21](media/image21.png)

     Metoda czytająca dane:

     ![image22](media/image22.png)

1. Przenieś metodę czytającą dane do osobnej klasy np. VegetablesRepository

   ```java
   public class VegetableRepository {
    private static final String TAG = "VegetableRepository";
    private final Context context;

    public VegetableRepository(Context context) {
        this.context = context;
    }
   public List<VegetableItem> loadVegetablesItemFromRaw() {
        List<VegetableItem> list = new ArrayList<>();
        try(InputStream is = context.getResources().openRawResource(R.raw.vegetables);
   ```

1. Utwórz testy dla metod, adaptera, UI:

   W zależnościach dodaj:

   ```xml
    androidTestImplementation(libs.runner)
    androidTestImplementation(libs.monitor)
   ```

   - dla metod:

     ```java
          import static org.junit.Assert.*;

      import android.content.Context;
      import androidx.test.platform.app.InstrumentationRegistry;
      import androidx.test.ext.junit.runners.AndroidJUnit4;

      import org.junit.Before;
      import org.junit.Test;
      import org.junit.runner.RunWith;

      import java.util.List;

      import gac.andrzej.cw15spinnerbaseadapternew.model.VegetableItem;

      @RunWith(AndroidJUnit4.class)
      public class VegetableRepositoryTest {

          private VegetableRepository repository;
          private Context context;

          @Before
          public void setUp() throws Exception {
              // Pobieramy prawdziwy kontekst aplikacji, żeby mieć dostęp do R.raw.vegetables
              context = InstrumentationRegistry.getInstrumentation().getTargetContext();
              repository = new VegetableRepository(context);
          }

          @Test
          public void loadVegetablesFromRaw() {
              // 1. Wykonanie akcji
              List<VegetableItem> vegetables = repository.loadVegetablesItemFromRaw();

              // 2. Sprawdzenie wyników (Asercje)
              assertNotNull("Lista nie powinna być nullem", vegetables);
              assertTrue("Lista powinna zawierać elementy (sprawdź plik vegetables.raw)", vegetables.size() > 0);

              // Opcjonalnie: sprawdź czy pierwszy element ma dane
              VegetableItem first = vegetables.get(0);
              assertFalse("Nazwa nie może być pusta", first.getName().isEmpty());
              assertFalse("Opis nie może być pusty", first.getDescription().isEmpty());
          }

          @Test
          public void loadVegetablesFromRawLog() {
              // Metody logujące trudno testować automatycznie,
              // ale możemy sprawdzić, czy metoda nie rzuca wyjątku 
              try {
                  repository.loadVegetablesFromRawLog();
              } catch (Exception e) {
                  fail("Metoda logująca rzuciła wyjątek: " + e.getMessage());
              }
          }
      }
     ```

- dla adaptera

     ```java
      public class MyAdapterTest {

      private MyAdapter adapter;
      private Context context;
      private List<VegetableItem> testItems;

      @Before
      public void setUp() {
          context = InstrumentationRegistry.getInstrumentation().getTargetContext();

          // Przygotowujemy dane testowe
          testItems = new ArrayList<>();
          testItems.add(new VegetableItem("Pomidor", "tomato.png", "Czerwony"));
          testItems.add(new VegetableItem("Błąd", "nieistnieje.png", "Brak obrazka"));

          adapter = new MyAdapter(context, testItems);
      }

      @Test
      public void getCount_returnsCorrectSize() {
          assertEquals("Adapter powinien mieć 2 elementy", 2, adapter.getCount());
      }

      @Test
      public void getView_setsCorrectDataToViews() {
          // 1. Pobieramy widok dla pierwszego elementu (Pomidor)
          View view = adapter.getView(0, null, null);

          // 2. Szukamy komponentów wewnątrz napompowanego layoutu
          TextView nameView = view.findViewById(R.id.nameView);
          TextView descView = view.findViewById(R.id.descView);
          ImageView imageView = view.findViewById(R.id.imageView);

          // 3. Asercje - sprawdzamy czy tekst się zgadza
          assertEquals("Pomidor", nameView.getText().toString());
          assertEquals("Czerwony", descView.getText().toString());
          assertNotNull("ImageView powinien istnieć", imageView);
      }
      }
     ```

- dla UI przy użyciu biblioteki Espresso

     ```java
          public class MainActivityTest {

      // Uruchamia MainActivity przed każdym testem
      @Rule
      public ActivityScenarioRule<MainActivity> activityRule =
              new ActivityScenarioRule<>(MainActivity.class);

      @Test
      public void testSpinnerSelection_updatesUI() {
          // 1. Sprawdź czy Spinner jest widoczny
          onView(withId(R.id.spinner)).check(matches(isDisplayed()));

          // 2. Kliknij w Spinner, aby otworzyć listę
          onView(withId(R.id.spinner)).perform(click());

          // 3. Wybierz element ze Spinnera (szukamy obiektu typu VegetableItem)
          onData(allOf(is(instanceOf(VegetableItem.class))))
                  .atPosition(1) // kliknij drugi element na liście
                  .perform(click());

          // 4. (Opcjonalnie) Sprawdzenie Toasta jest trudne w Espresso (wymaga customowych matcherów),
          // ale możemy sprawdzić czy Spinner teraz wyświetla wybrany element.
          onView(withId(R.id.spinner)).check(matches(isDisplayed()));
      }

  }

     ```

1. KONIEC.🔚
