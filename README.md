# Tugas9_MuhammadAhnafMaulana_5311421074
# Module 4
## Teknik Pencarian Blind Search (Breadth First Search)

#### Penjelasan
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/e7fbaf92ac80a6283339743497efda1c60274b9d/Praktikum4/img/Metode_BFS.jpeg?raw=true)
Pada module 4 BSF digunakan untuk melakukan atau mencari suatu goal state dari initial statenya dengan metode yang bisa dilihat pada gambar diatas. 

Pada Metode tersebut semua node pada level n akan dikunjungi  terlebih dahulu sebelum mengunjungi node-node pada level n+1. Pencarian dimulai dari node akar terus ke level ke-1 dari kiri ke kanan, kemudian berpindah ke level berikutnya demikian pula dari kiri ke kanan hingga ditemukannya solusi. 

## Tugas

- Tentukan bagaimana algoritma BFS di atas dapat menentukan node ke 8, 6, dan 7. dari ([sc, Tugas no 1](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/e7fbaf92ac80a6283339743497efda1c60274b9d/Praktikum4/src/tugas1.java))
- Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.6 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 5. 
- Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.5 dapat dibentuk.  Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 9
- Ubahlah kode program di atas sehingga bentuk tree seperti Gambar 4.7 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node C
Note : Gambar terdapat pada Module praktikum

#### Jawab
- Algoritma BFS dalam program di atas digunakan untuk mencari jarak terpendek dari node awal (dalam kasus ini, node n3) ke semua node lain dalam graph. Algoritma ini juga akan menentukan node yang dijangkau dengan menyusuri graph secara berlapis (layer by layer) dari node awal.
Algoritma dimulai dengan menginisialisi semua node dalam grapgh dengan beberapa parameter, salah satunya yaitu distace (jarak). Kemudian n3 (node 3) diinisiasi dengan jarak = 0. dan algoritma akan menjelajahi node awal (node3). Selanjutnya algoritma akan menjelajahi node node yang berdekatan (distancenya kecil = 1) yaitu node 4 dan node 2. Selanjutnya algoritma akan mengunjungi node 5, 6, dan 1 dengan distance 2 dari jarak awal. Dan yang terakhir akan mengunjungi node 7 dan node 8. Maka dari itu, BFS dalam menentukan node 8, 6, dan ke 7 dapat dilakukan dengan dengan memperhatikan distance antar node dengan node awal. hasil dari distancenya dapat dilihat pada gambar berikut
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno1.jpeg?raw=true)
- Lalu pada soal berikutnya, ubah static void main dr soal 1 agar menjadi tree pada gambar 4.5. static void main dapat dilihat pada code dibawah dan akan diubah nilainya untuk membuat tree seperti yang diperintahkan denagan sc yang saya buat ([sc, Tugas no 2](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/src/tugas2.java))
```sh
public static void main(String[] args){
            AdjacencyList graph = new AdjacencyList();
            Node n1 = new Node(1);
```
Lalu sc yang dijalankan akan memberikan desain tree yang diminta, dan node 5 didapatkan pada layer 2 dari node awal berdasarkan distancenya yaitu 2
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno2.jpeg?raw=true)
- Ubah code yang sebelumnya agar menjadi desain tree yang diminta ([sc, Tugas no 3](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/src/tugas3.java))
Lalu jalankan dan akan memberikan hasil sebagai berikut
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno3.jpeg?raw=true)
node 9 ditemukan pada layer 3 dikarenakan distancenya dengan node awal yaitu berjarak 3.
- Selanjutnya ubah code untuk memberikan desain tree pada gambar 4.7. Untuk desain tree yang digunakan menggunakan huruf, maka tipe data pada node diubah terlebih dahulu menjadi char. 
```sh
public static class Node
    {
        char data;
        int distance;
        Node predecessor;
        NodeColour colour;
            public Node(char data)
                {
                this.data = data;
                }
        public String toString()
            {
            return "(" + data + ",d=" + distance + ")";
            }
    }
```
Selanjutnya saya ubah code manjadi ([sc, Tugas no 4](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/src/no4.java)), lalu menghasilkan desain tree sebagai berikut :
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno4.jpeg?raw=true)
Dapat dilihat, bahwa BFS dapat menentukan node C pada layer 3 dikarenakan distancenya dengan node awalnya (node F) bernilai 3.

# Module 5
## TEKNIK HEURISTIC SEARCH (Heuristic Search)
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Dillinger is a cloud-enabled, mobile-ready, offline-storage compatible,
AngularJS-powered HTML5 Markdown editor.

- Type some Markdown on the left
- See HTML in the right
- ✨Magic ✨

## Features

- Import a HTML file and watch it magically convert to Markdown
- Drag and drop images (requires your Dropbox account be linked)
- Import and save files from GitHub, Dropbox, Google Drive and One Drive
- Drag and drop markdown and HTML files into Dillinger
- Export documents as Markdown, HTML and PDF

Markdown is a lightweight markup language based on the formatting conventions
that people naturally use in email.
As [John Gruber] writes on the [Markdown site][df1]

> The overriding design goal for Markdown's
> formatting syntax is to make it as readable
> as possible. The idea is that a
> Markdown-formatted document should be
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions.

This text you see here is *actually- written in Markdown! To get a feel
for Markdown's syntax, type some text into the left window and
watch the results in the right.

## Tech

Dillinger uses a number of open source projects to work properly:

- [AngularJS] - HTML enhanced for web apps!
- [Ace Editor] - awesome web-based text editor
- [markdown-it] - Markdown parser done right. Fast and easy to extend.
- [Twitter Bootstrap] - great UI boilerplate for modern web apps
- [node.js] - evented I/O for the backend
- [Express] - fast node.js network app framework [@tjholowaychuk]
- [Gulp] - the streaming build system
- [Breakdance](https://breakdance.github.io/breakdance/) - HTML
to Markdown converter
- [jQuery] - duh

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

## Installation

Dillinger requires [Node.js](https://nodejs.org/) v10+ to run.

Install the dependencies and devDependencies and start the server.

```sh
cd dillinger
npm i
node app
```

For production environments...

```sh
npm install --production
NODE_ENV=production node app
```

## Plugins

Dillinger is currently extended with the following plugins.
Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantaneously see your updates!

Open your favorite Terminal and run these commands.

First Tab:

```sh
node app
```

Second Tab:

```sh
gulp watch
```

(optional) Third:

```sh
karma test
```

#### Building for source

For production release:

```sh
gulp build --prod
```

Generating pre-built zip archives for distribution:

```sh
gulp build dist --prod
```

## Docker

Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the
Dockerfile if necessary. When ready, simply use the Dockerfile to
build the image.

```sh
cd dillinger
docker build -t <youruser>/dillinger:${package.json.version} .
```

This will create the dillinger image and pull in the necessary dependencies.
Be sure to swap out `${package.json.version}` with the actual
version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on
your host. In this example, we simply map port 8000 of the host to
port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart=always --cap-add=SYS_ADMIN --name=dillinger <youruser>/dillinger:${package.json.version}
```

> Note: `--capt-add=SYS-ADMIN` is required for PDF rendering.

Verify the deployment by navigating to your server address in
your preferred browser.

```sh
127.0.0.1:8000
```

## License

MIT

**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>

