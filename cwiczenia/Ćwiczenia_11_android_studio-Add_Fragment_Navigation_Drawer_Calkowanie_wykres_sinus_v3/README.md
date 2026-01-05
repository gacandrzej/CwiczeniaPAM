Ćwiczenia 11 -- Android studio -- Navigation Drawer, Canvas, add
fragment
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Otwórz projekt z ćwiczeń 10 o nazwie MyNavigationDrawer.
2.  Otworzyć dokumentację:
<https://developer.android.com/guide/fragments?gclid=CjwKCAiAhreNBhAYEiwAFGGKPB_HJINJ1lKxOEHCh_a6-J-qbiBDX5-uWjgNClL3gnSVj57fsaa8ihoCvmsQAvD_BwE&gclsrc=aw.ds>
<https://developer.android.com/guide/fragments/create>
<https://developer.android.com/guide/fragments/fragmentmanager>
3.  Uruchom aplikację:
> ![](media/image1.png)
4.  Dodaj fragmenty i aktywności:
5.  Dodaj layout layout -\> Layout Resource File (file name:
    home_fragment
change costraint to relative , add
android:background=\"@color/teal_200\"
6.  Dodaj textview:
\<TextView
android:layout_width=\"wrap_content\"
android:layout_height=\"wrap_content\"
android:layout_centerInParent=\"true\"
android:textSize=\"25sp\"
android:text=\"Home fragment\"
android:textColor=\"@color/white\"\>
\</TextView\>
7.  Skopiuj home_fragment i wklej -\> i zmień nazwę na:
rectangle_fragment,
trapeze_fragment
simpson fragment
8.  Dodaj klasę New -\> Java Class add class HomeFragment extend
    Fragment
9.  Ctrl+o lub Alt+Insert lub prawy myszy Generate\... i dodać metodę
    override :
public View onCreateView(\...)
10. Zmień return na: return
    inflater.inflate(R.layout.home_fragment,container,false);
11. zaimportuj: **import** androidx.fragment.app.Fragment;
![](media/image2.png)
12. Skopiuj HomeFragment.java i wklej, zmień nazwę na:
RectangleFragment,
TrapezeFragment
SimpsonFragment
13. Dodaj pustą aktywność Empty Activity, o nazwie DrawSinus
14. W aktywności activity_draw_sinus.xml zmień layout na RelativeLayout
15. Dodaj textview:
\<TextView
android:layout_width=\"wrap_content\"
android:layout_height=\"wrap_content\"
android:text=\"here draw function sinus\"
android:textSize=\"35sp\"
android:layout_centerInParent=\"true\"\>
\</TextView\>
16. Dodaj w MainActivity.java
NavigationView navigationView = findViewById(R.id.navigation_view);
navigationView.setNavigationItemSelectedListener(this);
![](media/image3.png)
17. (czerwona żarówa) i public class MainActivity extends
    AppCompatActivity implements
    NavigationView.OnNavigationItemSelectedListener
18. Dodaj również \@Override
public boolean onNavigationItemSelected(@NonNull MenuItem item)
return false;
19. Zamień return false na return true;
20. Dodaj
    getSupportFragmentManager().beginTransaction().replace(R.id.Fragment_container,new
    HomeFragment());
21. W metodzie public boolean onNavigationItemSelected(@NonNull MenuItem
    item) and dodaj:
switch (item.getItemId())
case R.id.home:
getSupportFragmentManager().beginTransaction().replace(R.id.Fragment_container,
new HomeFragment()).commit();
break;
22. Dodaj następne pozycje case dla id z pliku drawer_menu.xml
23. Dodaj case R.id.sinus:
Intent intent = new Intent(getApplicationContext(),DrawSinus.class);
startActivity(intent);
break;
24. Powinieneś uzyskać:
![](media/image4.png)
25. Dodaj przed return true w powyższym drawerLayout.closeDrawers();
26. Dodaj klasę MyViewDrawSinus extends View
27. Dodaj metodę onDraw(Canvas canvas)
![](media/image5.png)
28. W klasie DrawSinus create object MyViewDrawSinus
29. Dodaj w MainActivity.java
if(savedInstanceState == null)
getSupportFragmentManager().beginTransaction().replace(R.id.Fragment_container,new
HomeFragment()).commit();
navigationView.setCheckedItem(R.id.home);
![](media/image6.png)
30. Sprawdź rysowanie poszczególnych funkcji, np.: sinus
> ![](media/image7.png)
31. Dodaj obsługę fragmentów dla całkowania numerycznego, np.:
![](media/image8.png)
32. Dodaj potrzebne EditText, TextView do realizacji powyższej metody i
    dwóch pozostałych, do fragmentu w xml.( Dodaj podpowiedź do pola
    EditText, hint), np.:
![](media/image9.png)
33. Zadania dodatkowe:
    a)  zaprojektuj obsługę ostrzegania użytkownika o nie wpisaniu
        danych do któregoś z pól.
![](media/image10.png)
b)  dodaj obsługę ostrzegania użytkownika o podaniu niepoprawnego
    formatu danych
c)  przeprowadź debugowanie dla pętli
<!-- -->
34. KONIEC.
