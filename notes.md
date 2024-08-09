        buildPhase = ''
          pandoc resume.md \
          -t html -f markdown \
          -c style.css --self-contained \
          -o resume.html

          wkhtmltopdf --enable-local-file-access \
          resume.html \
          resume.pdf


        apt install -y pandoc
        apt install weasyprint

        https://doc.courtbouillon.org/weasyprint/stable/first_steps.html#command-line

        ln -fs /usr/share/zoneinfo/Europe/Warsaw /etc/localtime
        apt update
        #DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata
        #dpkg-reconfigure --frontend noninteractive tzdata
        apt install -y pandoc weasyprint

        pandoc [file-name].md --pdf-engine=weasyprint --css=pdf-styles.css -o [file-name].pdf
        pandoc resume.md --pdf-engine=weasyprint --css=style.css -o resume-test.pdf