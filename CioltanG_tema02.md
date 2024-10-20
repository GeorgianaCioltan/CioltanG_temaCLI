1. GL.Ortho(-1.0, 5.0, -5.0, 5.0, 0.0, 4.0);

    S-a indepartat triunghuiul si s-a mutat mai la stanga

3.
        1.Viewport este fereastra pe care o vede player-ul in scena 3D, in functie de POV-ul lui.
        2.FPS reprezinta cate imagini sunt randate per secunda. Cu cat mai putine imagini per secunda (10fps) filmul sau jocul se vede sacadat, iar la un fps mai mare se vede mai fluid.
        3.OnUpdateFrame() se execută înainte de fiecare desenare a imaginii pe ecran și este folosită pentru a actualiza mișcările sau logica jocului.
        4.Modul imediat este o metodă veche în care fiecare punct dintr-un obiect este desenat imediat. Este ușor de folosit, dar lent și ineficient.
        5.OpenGL 3.0 este ultima versiune care suportă modul imediat. În versiunile mai noi, acesta nu mai este folosit.
        6.Metoda OnRenderFrame() se execută la fiecare cadru și este responsabilă de desenarea efectivă a scenei pe ecran la fiecare frame.
        7.Această metodă ajustează desenul scenei pentru a se potrivi cu dimensiunea ferestrei. Fără aceasta, imaginea ar putea fi distorsionată.
        8.Acești parametri controlează cum vezi scena:

                fovY: cât de larg este câmpul vizual.
                aspectRatio: raportul între lățimea și înălțimea ferestrei.
                nearClip: distanța minimă la care obiectele devin vizibile.
                farClip: distanța maximă până la care vezi obiectele.