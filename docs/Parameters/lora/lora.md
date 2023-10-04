# LoRA (Low Rank Adaptation)

LoRA, or **Low Rank Adaptation**, is an optional model that can be appended to the generation. Each LoRA adds a small neural network to the original model, aiming to influence it towards its specific generative goal. By adding `--lora` followed by the name of the LoRA model to be used, you can add it to the generation. 

By default, no LoRAs are used unless specifically asked for by the user.

Up to 5 LoRAs can be used at any single time, but their individual influence is reduced by every additional LoRA model. This is automatically done by Distillery's backend in order to preserve the quality of the generative output, since too many LoRAs may generate additional noise in the final product.

!!! tip "How LoRAs actually work"
    A LoRA is controlled by two main parameters: its **weight**, which determines how strongly its influence must be on the original model's output, and its **activation keywords**, which are the words that must be used in order to let the LoRA know it must work. Distillery is handling the weight of the LoRA automatically, so the only thing the user must focus on is the generation prompt.

While the best LoRAs will always be the ones trained over the model that is invoked for the generation, most LoRAs can be ported from one model checkpoint to another of the same family (that is: SD1.5-based LoRAs work across most SD1.5 model checkpoints, and the same goes for SDXL). 

LoRAs are unique tools at our disposal in the generative art toolkit. Think of them as "cartridges" to the model checkpoints' "consoles".

## Loras for SD 1.5 models

The following LoRAs are available for our standard models (bloodymary, vodka and screwdriver):


| LoRA name  | Creator  | Description  | Activation words  | Available In                        |
|------------|----------|--------------|-------------------|-------------------------------------|
| ```animeminimalist``` | [hortacreator](https://civitai.com/user/hortacreator/models) | Minimalist Anime Style | ```anime minimalist``` | [Link](https://civitai.com/models/24833/minimalist-anime-style) |
| ```architecture``` | [xjdeng](https://civitai.com/user/xjdeng/models) | Photorealistic architectural images | ```amazingarchitecture``` | [Link](https://civitai.com/models/107455?modelVersionId=125987) |
| ```atmosphere``` | [Eisthol](https://civitai.com/user/Eisthol/models) | Adds details and ambiance to a scene | ```None``` | [Link](https://civitai.com/models/75164/atmosphere) |
| ```badvhs``` | [zarxrax](https://civitai.com/user/zarxrax/models) | Old, poor-quality VHS tape | ```vhs footage, vhs``` | [Link](https://civitai.com/models/3679/bad-vhs) |
| ```barbie``` | [RIXYN](https://tensor.art/u/628134534906582880) | Makes anything Barbie | ```ts_barbie``` | [Link](https://civitai.com/models/73934/barbie-or-toy-story-3) |
| ```bladerunner``` | [luisa_pinguin](https://twitter.com/LuisaCoolSouza) | Makes Blade Runner 2049 movie stills | ```moviestill``` | [Link](https://civitai.com/models/5566/luisap-bladerunner2049-still-lora) |
| ```caravaggio``` | [Ashley_Jones_fan](https://civitai.com/user/Ashley_Jones_fan/models) | Artist LoRA: Caravaggio oil paintings | ```CARAVAGGIO``` | [Link](https://civitai.com/models/119790/caravaggio-oil-painting-style) |
| ```caricature``` | [vizsumit](https://civitai.com/user/vizsumit/models) | Caricature style | ``` caricature``` | [Link](https://civitai.com/models/56978/cartoon-caricature) |
| ```charactersheet``` | [YeiyeiArt](https://tensor.art/u/612567052280105600) | Creates character design sheets | ```CharacterSheet``` | [Link](https://civitai.com/models/100435/character-design-sheet-helper-3-perspectives-comissions-opens-by-yeiyeiart) |
| ```davinci``` | [DarkBeam](https://civitai.com/user/DarkBeam) | Artist LoRA: Leonardo da Vinci oil paintings | ```wjqleonardo``` | [Link](https://civitai.com/models/63331/leonardo-da-vinci-style) |
| ```environmentart``` | [Petybear](https://civitai.com/user/Petybear/models) | Environment art & scenery | ```None``` | [Link](https://civitai.com/models/93826?modelVersionId=120191) |
| ```foodphoto``` | [leroidoesaiart](https://civitai.com/user/leroidoesaiart) | Food photography | ```foodphoto``` | [Link](https://civitai.com/models/45322/food-photography) |
| ```futuristicscape``` | [fitcorder](https://linktr.ee/fitcorder) | Makes detailed, futuristic spaces and landscapes | ```None``` | [Link](https://civitai.com/models/58764?modelVersionId=92193) |
| ```gothicdress``` | [cyberAngel_](https://civitai.com/user/cyberAngel_/models) | Gothic style dress | ```lo_dress``` | [Link](https://civitai.com/models/65283?modelVersionId=116611) |
| ```gta``` | [vizsumit](https://civitai.com/user/vizsumit/models) | GTA style drawings | ```comic character``` | [Link](https://civitai.com/models/66719?modelVersionId=161686) |
| ```isometric``` | [CitronLegacy](https://civitai.com/user/CitronLegacy/models) | Isometric views | ```Isometric_Setting``` | [Link](https://civitai.com/models/118775/stylized-setting-isometric) |
| ```isometricdnd``` | [Tomas_Aguilar](https://civitai.com/user/Tomas_Aguilar) | Isometric interiors for D&D/RPG | ```isometricclas2nive, isometricnive``` | [Link](https://civitai.com/models/80719/table-rpg-dandd-maps-isometric-room) |
| ```kurzgesagt``` | [chilon249](https://civitai.com/user/chilon249/models) | Kurzgesagt drawing style | ```kurzgesagt, vector art``` | [Link](https://civitai.com/models/10098?modelVersionId=12006) |
| ```marble``` | [daemonrat](https://civitai.com/user/daemonrat/models) | Makes marble statues | ```marblee style, marblee, marblesh ``` | [Link](https://civitai.com/models/7702/marblesh-lora-extraction) |
| ```oilpainting``` | [nnna](https://civitai.com/user/nnna/models) | Oil painting style | ```None``` | [Link](https://civitai.com/models/107165/oil-painting-stick) |
| ```pixhell``` | [SPYBG](https://civitai.com/user/SPYBG/models) | Alternative pixel art LoRA | ```pixelart``` | [Link](https://civitai.com/models/21270/pixhell-15-lora) |
| ```psychedelicnoir``` | [Ciro_Negrogni](https://linktr.ee/ciro_negrogni) | Intricate noir patterns and surreal imagery | ```psychedelic_noir``` | [Link](https://civitai.com/models/120638?modelVersionId=131218) |
| ```rootsbranches``` | [konyconi](https://civitai.com/user/konyconi/models) | Makes objects sprout roots and branches | ```RootsBranchesAI``` | [Link](https://civitai.com/models/63660/rootsbranchesai) |
| ```saltbae``` | [FallenIncursio](https://civitai.com/user/FallenIncursio/models) | Makes the Salt Bae meme position | ```SaltBaeMeme``` | [Link](https://civitai.com/models/106212/salt-bae-meme-or-concept-lora) |
| ```space``` | [edobgames](https://civitai.com/user/edobgames/models) | Model that enhances images from space | ```space, planet, galaxy, star``` | [Link](https://civitai.com/models/44667/syfyeye1) |
| ```starwars``` | [Lykon](https://tensor.art/u/600303455797521413) | Star Wars style | ```star wars``` | [Link](https://civitai.com/models/105329/star-wars-style-lora) |
| ```vermeer``` | [Ashley_Jones_fan](https://civitai.com/user/Ashley_Jones_fan/models) | Artist LoRA: Vermeer oil paintings | ```VERMEER``` | [Link](https://civitai.com/models/118054/vermeer-oil-painting-style-for-portraits) |
| ```victoriandress``` | [cyberAngel_](https://civitai.com/user/cyberAngel_/models) | Victorian style classical dress | ```lodress``` | [Link](https://civitai.com/models/65283?modelVersionId=116611) |
| ```voidenergy``` | [konyconi](https://civitai.com/user/konyconi/models) | Magical blue-violet setting (good for RPG/fantasy horror) | ```V0id3nergy``` | [Link](https://civitai.com/models/60553/kvoidenergy) |
| ```water``` | [DitamAi](https://twitter.com/DitamAi_) | Create more consistent water | ```water, stream of water, water balls``` | [Link](https://civitai.com/models/10750/watervfx-create-more-consistent-water-wip) |


## Loras for SDXL models

We currently only have one LoRA for SDXL: ```lora nurlens```, a realism LoRA.
