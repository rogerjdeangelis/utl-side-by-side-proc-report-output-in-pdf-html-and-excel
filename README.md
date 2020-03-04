# utl-side-by-side-proc-report-output-in-pdf-html-and-excel
Side by side proc report output in pdf html and excel
    Side by side proc report output in pdf html and excel

    github
    https://tinyurl.com/v69rhu6
    https://github.com/rogerjdeangelis/utl-side-by-side-proc-report-output-in-pdf-html-and-excel

    Outputs  ( note you can download the entire repository using the gree clone or dowload option on the fist page)

    PDF  ( can be viewed directly on github)
    https://tinyurl.com/qqzrrx2
    https://github.com/rogerjdeangelis/utl-side-by-side-proc-report-output-in-pdf-html-and-excel/blob/master/side_by_side.pdf

    EXCEL (you need to download the entire repo and unzip - github does not support an excel viewer)
    https://github.com/rogerjdeangelis/utl-side-by-side-proc-report-output-in-pdf-html-and-excel

    HTML (you need to download the entire repo and unzip - github does not support an excel viewer)
    https://github.com/rogerjdeangelis/utl-side-by-side-proc-report-output-in-pdf-html-and-excel

    ODS excel does not support side by side proc reports?

    You can export the HTML to excel using these steps below.

    1. Open the html in internet explorer (not chrome). 
    2. Right click (anywhere) and select 'export to MS excel'.
    3. A pop up will display the html with options4.
    4. Click on 'import' in lower right corner5.
    5. Click ok and cloose a location to save

    You can also create side by side reports in excel using the libname engine, R or Python.

    For additiona options
    https://tinyurl.com/vxfjzqh
    https://github.com/rogerjdeangelis?tab=repositories&q=side+by+side&type=&language=
    https://github.com/rogerjdeangelis/utl_side_by_side_excel_reports
    https://tinyurl.com/yesqc2ah
    https://github.com/rogerjdeangelis/utl_excel_add_to_sheet

    SAS-L:
    https://listserv.uga.edu/cgi-bin/wa?A2=SAS-L;3ab6be07.2003a

    *_                   _
    (_)_ __  _ __  _   _| |_
    | | '_ \| '_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    ;

    data math;
      set sashelp.class(obs=5 keep=name sex age);
    run;quit;

    data civics;
      set sashelp.class(firstobs=15 keep=name sex age);
    run;quit;

    obs WORK.MATH total obs=5

       NAME     SEX    AGE

      Joyce      F      11
      Louise     F      12
      Alice      F      13
      James      M      12
      Thomas     M      11


    WORK.CIVICS total obs=5

       NAME     SEX    AGE

      Joyce      F      11
      Louise     F      12
      Alice      F      13
      James      M      12
      Thomas     M      11

    *            _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| '_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    ;

    In html, pdf and excel

              MATH CLASS               CIVICS CLASS

         NAME     SEX    AGE       NAME     SEX    AGE

        Joyce      F      11      Joyce      F      11
        Louise     F      12      Louise     F      12
        Alice      F      13      Alice      F      13
        James      M      12      James      M      12
        Thomas     M      11      Thomas     M      11

    *
     _ __  _ __ ___   ___ ___  ___ ___
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
               _  __
     _ __   __| |/ _|
    | '_ \ / _` | |_
    | |_) | (_| |  _|
    | .__/ \__,_|_|
    |_|
    ;

     %utlfkil(d:/pdf/side_by_side.pdf);  * delete;

     options orientation=landscape;
     ods pdf file="d:/pdf/side_by_side.pdf";
     ods layout gridded columns=2 column_widths=(47% 47%) column_gutter=1pct;
     ods region;
     proc report data=math nowd missing
        style(report)={outputwidth=100pct}
        style(header)={font_size=13pt}
        style(column)={font_size=12pt just=c}
    ;
     cols ("Math Class" name age sex);
     run;quit;
     ods region;
     proc report data=Civics nowd missing
        style(report)={outputwidth=100pct}
        style(header)={font_size=13pt}
        style(column)={font_size=12pt just=c}
    ;
        cols ("Civics Class" name age sex);
     run;quit;
    ods layout end;
    ods pdf close;

    *_     _             _
    | |__ | |_ _ __ ___ | |
    | '_ \| __| '_ ` _ \| |
    | | | | |_| | | | | | |
    |_| |_|\__|_| |_| |_|_|

    ;

     %utlfkil(d:/pdf/side_by_side.htm);

     options orientation=landscape;
     ods html path="d:/htm" body="side_by_side..htm";
     ods layout gridded columns=2 column_widths=(47% 47%) column_gutter=1pct;
     ods region;
     proc report data=math nowd missing
        style(report)={outputwidth=100pct}
        style(header)={font_size=13pt}
        style(column)={font_size=12pt just=c}
    ;
     cols ("Math Class" name age sex);
     run;quit;
     ods region;
     proc report data=civics nowd missing
        style(report)={outputwidth=100pct}
        style(header)={font_size=13pt}
        style(column)={font_size=12pt just=c}
    ;
     cols ("Civics Class" name age sex);
     run;quit;
    ods layout end;
    ods html close;


