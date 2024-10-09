# Pengisian EPBM IPB Secara Otomatis

## Step
- Buka [Student Portal IPB](https://studentportal.ipb.ac.id/Akademik/EPBM)
- Pilih salah satu matkul dan **hanya untuk matkul** bukan prasana
- Buka Console Browser (Ctrl + shift + j) / (klik f12 pilih console)
- Copy dan paste kode di bawah ini *

```
async function setStart() {
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
        await setStart();
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
## HIMBAUAN!!!!
- Jika terdapat warning Don't Paste seperti gambar dibawah. Bisa **Ketik** `allow pasting` tekan **Enter** lalu copy dan paste kode di atas
  ![image](https://github.com/user-attachments/assets/74550e1f-546a-4716-82cc-5708c073bcd2)

