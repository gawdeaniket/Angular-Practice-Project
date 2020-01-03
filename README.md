
https://medium.com/@george.seif94/a-full-tutorial-on-how-to-use-github-88466bac7d42
https://appdividend.com/2018/05/25/angular-6-file-upload-tutorial/
https://stackoverflow.com/questions/51989482/adding-http-headers-in-angular-6/52100181
https://stackoverflow.com/questions/47936183/angular-file-upload
https://bootsnipp.com/snippets/MaA0A
https://www.npmjs.com/package/ngx-pagination
https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-tables.php
https://www.primefaces.org/primeng/#/datatable/paginator
https://ciphertrick.com/search-sort-pagination-angular/
https://stackblitz.com/edit/angular-blob-file-download
https://stackoverflow.com/questions/35138424/how-do-i-download-a-file-with-angular2


public validateForm(formToValidate: FormGroup, formErrors: any, checkDirty?: boolean) {
    const form = formToValidate;
    for (const field in formErrors) {
      if (field) {
        formErrors[field] = '';
        const control = form.get(field);

        const messages = this.validationMessages();
        if (control && !control.valid) {
          if (!checkDirty || (control.dirty || control.touched)) {
            for (const key in control.errors) {
              if (key && key !== 'invalid_characters') {
                formErrors[field] = formErrors[field] || messages[key];
              } else {
                formErrors[field] = formErrors[field] || messages[key](control.errors[key]);
              }
            }
          }
        }
      }
    }

    return formErrors;
  }
