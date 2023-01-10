# MemeGenerator

### Веб-приложение для создания своего мема [Meme Generator](https://memecreate.netlify.app/ "Click me!")
В процессе прохождения курса по изучению библиотеки React создала данное веб-приложение для закрепления полученных знаний.

![First screen](https://github.com/Kartiina/MemeGenerator/blob/master/images/screenshots/first.png "first thing we see")

>На данный момент не было времени заниматься дизайном, поэтому больший упор был сделан на функционал

![Second screen](https://github.com/Kartiina/MemeGenerator/blob/master/images/screenshots/find%20some%20pic.png "find a pic that we like")

Картинки брались из API, реализация показана ниже:
```js
const[allMemes, setAllMemes] = React.useState([])

    React.useEffect(() => {
        async function getMemes(){
            const res = await fetch("https://api.imgflip.com/get_memes")
            const data = await res.json()
            setAllMemes(data.data.memes)
        }
        getMemes()
    }, [])

    function getMemeImage() {
        const randomNumber = Math.floor(Math.random() * allMemes.length)
        const url = allMemes[randomNumber].url
        setMeme(prevMeme => ({
            ...prevMeme,
            randomImage: url
        }))
    }
 ```
 
 Дальше происходит главный этап в создании мема - нужно придумать в чем мем.<br/>
 Итак, пользователь вводит верхнюю подпись в левый инпут и нижнюю в, соответственно, правый. Получается смешная картинка! <br/>
 <br/>
 
 ![Third screen](https://github.com/Kartiina/MemeGenerator/blob/master/images/screenshots/result.png "your meme!")
 #
 На этом разработка данного проекта не заканчивается, я планирую сделать более привлекательный дизайн, а также возможность скачивать полученную картинку на свое устройство или делиться ей.
 ## tnx for your attention!👻

**@3d.karttina**
