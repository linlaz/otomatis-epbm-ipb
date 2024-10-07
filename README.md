# Pengisian EPBM IPB Secara Otomatis

## Step
- Buka [Student Portal IPB](https://studentportal.ipb.ac.id/Akademik/EPBM)
- Pilih salah satu matkul
- Buka Console Browser (Ctrl + shift + j) / (klik f12 pilih console)
- Copy and paste kode di bawah ini

```
async function SetStart() {
    return new Promise((resolve) => {
        const temp = document.getElementsByClassName("form-control");

        for (let index = 1; index < temp.length; index++) {
                temp[index].children[3].click();
        }
        resolve();
    });
}

const list = document.getElementsByClassName("list-group").length;

(async function executeWithDelay() {
    for (let i = 2; i <= list - 1; i++) {
        await SetStart();
        document.getElementsByClassName("btn-primary")[0].click();
        await new Promise((resolve) => setTimeout(resolve, 500));
    }
    
    document.querySelectorAll('input[type="checkbox"]')[0].click();
    await new Promise((resolve) => setTimeout(resolve, 500));
    document.getElementsByClassName("btn-primary")[0].click();
    await new Promise((resolve) => setTimeout(resolve, 500));
    document.getElementsByClassName("swal2-confirm")[0].click();
})();
```
