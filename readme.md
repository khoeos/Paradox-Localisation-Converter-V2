<!-- PROJECT LOGO -->
# <a href="https://github.com/khoeos/Paradox-mod-language-converter">Depecrated, New version here</a>
<br />
<p align="center">
  <p align="center">
    A simple app to generate localisation for your language, based on english version for Paradox's Games
    <br />
    <a href="https://github.com/khoeos/Paradox-Localisation-Converter-V2/releases"><strong>Download App »</strong></a>
    <br/>
    <br/>
    <a href="https://github.com/khoeos/Paradox-Localisation-Converter-V2">Explore the docs »</a>
    <br />
    <br />
    <a href="https://github.com/khoeos/Paradox-Localisation-Converter-V2/issues">Report Bug</a>
    ·
    <a href="https://github.com/khoeos/Paradox-Localisation-Converter-V2/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#how-it-work">How It Work</a>
    </li>
    <li>
      <a href="#debug-mode-and-logs">Debug mod and logs</a>
    </li>
    <li><a href="#todo">Todo</a></li>
    <li><a href="#other-paradox-games">Other Paradox Games</a></li>
    <li><a href="#stacks">Stacks</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
As non english player, one thing that annoys me in paradox game, it's the management of translations inside mods. If a modder take the choice to create localisation files to have translation in multiple languages, if there is no files for your language, inside the game you'll only see translation tag, not even the english (ore any languages) texts.

Even if you're good at english, it's a comfort to play with our native language for most of the content with only some untranslated mods in english.

So to help all the players like me, and the modders who want to be more inclusive easily, i made this app which do the job of generate localisation files for any selected language from english files (from other languages later).

The first version was a simple script not user friendly at all, so i decided to upgrade it and made a user interface to do that.

**At this time, the app is only tested with stellaris, but it theorically work with all paradox game, see more lower**

<!-- HOW IT WORK -->
## How it Work
*If you know french, everything is commented, the translation will come later. Every variables and functions are in english though*

The first step is to enter your mod folder location and select the language you want and click on translate.
1. The script will search for any .yml localisation file inside the mod folder and break down the file path
   - It will ignore any files outside the localisation folder
   - It will ignore any files that are not in the root of localisation folder or in english folder (i'll manage the selection of other base language than english later)
   - It will ignore the files in any replace folder (i'll manage it later, i know it's a thing for modpack creator)
   - It will ignore the files which don't have the `l_english` tag
2. Then, when only the correct files remain, it'll replace the english tag to the selected language tag in the name and in the content of the file
3. Then, remplace the path saved in the variable from english to selected language if in sub folder
4. It'll re-setup all the complete pathes for the new location file and folder and the path for the log file (explained lower)
5. finally, it'll try to add the new file in the folder, if the file already exist, it'll ignore and go to the next file

<!-- DEBUG MODE AND LOGS -->
## Debug mode and Logs
The app is made with electron, it's like a website extracted into a desktop app, so like any website you can access to the devtools which contain a lot of help to track and debug application.
So, to manage that everything work fine, i made 2 things.
1. The file logging, every added files is logged into a .addedfiles file in the localisation root of each mods, so with that you can track which files are added (if you don't see it, you have to enable the hidden files in the windows parameters)
2. Multiples console logging with and withouth a custom debug mod.

### Debug mode
Like any webApp you can access to the devtools with ctrl+maj+i
Access to the console tab to see some informations even without the custom debug mode.

#### Without debug mode
- You'll know where the script start and end and the languages selected.
- You'll know every path of base english file and of the new file.
- You'll be noticed if the file already exist

#### With debug mode
You can activate it by clicking in the button in the right bottom corner, it'll become full green and not stroked when activated.

It'll basically send a log for every variable selected or editted, splitted by 5 blocks. I'll add informations in the debugger later.

If it only show the first block it's perfectly normal, as a verification is made at this point to exclude some files. But for the rest, the blocks must finish with an already existing file or added file notification

<!-- OTHER PARADOX GAMES -->
## Other paradox games
Like i said, at this time i've only tested the app for Stellaris, but the game selector in the app is actually purely esthetic.

As the majority of paradox game manage the translation in the same way (CK3, EU4, Hoi4...) it'll normally work with them (hence the choice of the name), simply enter the mod folder path. 
As the script came with multiple filter to select the good file, it'll normally not make problems, and even if it's the case, as everything is locally, you'll juste have to re-install the game.

<!-- Stacks -->
## Stacks

This app was made of [Electron](https://www.electronjs.org/) by [Electron Forge](https://www.electronforge.io/) and [tailwind](https://tailwindcss.com/) with the use of [Directory-tree](https://www.npmjs.com/package/directory-tree).

### Installation
Verify you have [node and npm](https://nodejs.org/en/download/) installed with the actual LTS release
1. Clone the repository
2. Make `npm install`
3. Launch with `npm start`
  
### How to Build
Simply do `npm run make` and it'll build an executable for your OS.
Jump into the [electronForge documentation](https://www.electronforge.io/config/makers) for in depth configuration


<!-- TODO -->
## TODO

- Management of replace folders
- Set another base language
- Improve and translate the comments and console log
- Option to extract new files instead of add them directly into the mod folders
- Manage incomplete files (missing translation tag for example)
- Test for the other paradox games
- Improve the script
- Update with reacti
- Add loading bar while doing trad.
- Made the best icon !

See the [open issues](https://github.com/Khoeos/Paradox-mod-localisation-converter/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

Don't hesitate to pm me on discord to talk about the app. You can find my tag lower.



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Discord : Khoéos#9117

Project Link: [https://github.com/Khoeos/Paradox-mod-localisation-converter](https://github.com/Khoeos/Paradox-mod-localisation-converter)






<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/Khoeos/repo.svg?style=for-the-badge
[contributors-url]: https://github.com/Khoeos/Paradox-mod-localisation-converter/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Khoeos/repo.svg?style=for-the-badge
[forks-url]: https://github.com/Khoeos/Paradox-mod-localisation-converter/network/members
[stars-shield]: https://img.shields.io/github/stars/Khoeos/repo.svg?style=for-the-badge
[stars-url]: https://github.com/Khoeos/Paradox-mod-localisation-converter/stargazers
[issues-shield]: https://img.shields.io/github/issues/Khoeos/repo.svg?style=for-the-badge
[issues-url]: https://github.com/Khoeos/Paradox-mod-localisation-converter/issues
[license-shield]: https://img.shields.io/github/license/Khoeos/repo.svg?style=for-the-badge
[license-url]: https://github.com/Khoeos/Paradox-mod-localisation-converter/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/Khoeos
