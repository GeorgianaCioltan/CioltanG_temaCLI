1.OpenGL deseneaza vertexurile intr-o maniera antiorara (ccw) deoarece ordinea implictia este front face.

    
    GL.Begin(PrimitiveType.Lines);

    // Axa X - linie roșie de la (-1, 0) la (1, 0)
    GL.Color3(Color.Red);
    GL.Vertex2(-1.0f, 0.0f); // punctul din stânga
    GL.Vertex2(1.0f, 0.0f);  // punctul din dreapta

    // Axa Y - linie verde de la (0, -1) la (0, 1)
    GL.Color3(Color.Green);
    GL.Vertex2(0.0f, -1.0f); // punctul de jos
    GL.Vertex2(0.0f, 1.0f);  // punctul de sus

    GL.End();

2.Anti-aliasing-ul funcționează prin netezirea tranzițiilor de culoare de-a lungul marginilor unui obiect
        de exemplu:
            -Apropierea culorilor marginilor: Schimbă ușor culoarea pixelilor de la margine pentru a crea o tranziție graduală între culorile obiectului și fundal. Aceasta ajută ochiul să perceapă marginile ca fiind mai netede.
            -Supra-eșantionare (Super-sampling): O metodă comună de anti-aliasing în care o imagine este randată la o rezoluție mai mare decât cea finală și apoi scalată în jos. Acest lucru ajută la mediarea culorilor și detaliilor, obținând astfel linii mai netede.

3.Care este efectul rulării comenzii GL.LineWidth(float)? Dar pentru GL.PointSize(float)? Funcționează în interiorul unei zone GL.Begin()?
    -GL.LineWidth(float) ajustează grosimea liniilor pe care le desenezi, permițându-ți să creezi linii mai subțiri sau mai groase, în funcție de valoarea dată. 
    -GL.PointSize(float), pe de altă parte, modifică dimensiunea punctelor desenate, astfel încât să fie mai mari sau mai mici. 
Ambele comenzi trebuie apelate înainte de GL.Begin() și își vor aplica efectul asupra elementelor desenate între GL.Begin() și GL.End().

4.  -LineLoop leagă toate punctele desenate într-un ciclu, adică, după ce desenezi ultima linie, se va trasa o linie înapoi la primul punct, formând un poligon închis.
    -LineStrip conectează punctele desenate cu linii, dar nu se închide automat; doar primele și ultimele puncte rămân separate.
    -TriangleFan începe cu un punct central și leagă fiecare punct din listă cu acesta, formând triunghiuri ce se radiază din centrul ales, util pentru a crea forme circulare.
    -TriangleStrip folosește un set de puncte pentru a crea triunghiuri adiacente, fiecare triunghi partajând două vârfuri cu triunghiul anterior, ceea ce permite desenarea unor forme complexe cu mai puține puncte.

6.Utilizarea culorilor diferite în desenarea obiectelor 3D este importantă pentru a oferi profunzime și detalii vizuale, făcând obiectele să pară mai realiste. Culorile variate ajută la evidențierea formelor și contururilor, ceea ce îmbunătățește percepția vizuală a structurii obiectului. Gradientele pot sugera iluminarea și umbrele.

7.Gradient-ul de culoare reprezinta o tranzitie fina ochiului uman de la o culoare la alta urmarind un patternde tipul rgb. Un exemplu de gradient este de exemplul cerul la apus. De la V la E se formeaza un gradient de albstru inchis spre galben (alabstru-indigo-roz-rosu-portocaliu-galben).

10.Atunci când desenezi o linie sau un triunghi utilizând un mod de desenare de tip strip (de exemplu, GL_TRIANGLE_STRIP sau GL_LINE_STRIP) în OpenGL, utilizarea unei culori diferite pentru fiecare vertex are un impact direct asupra modului în care culoarea se va interpola între vârfuri (vertices) și, prin urmare, asupra aspectului final al formei desenate.
