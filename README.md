# Revealing contested memory - github repository
This repository contains the code for the Master thesis "Revealing contested memory: Automatic sensitive content detection in colonial photographic archives", aiming at developing Machine Learning models (specifically, Computer Vision models) to assess the feasibility of automatic sensitive content detection in colonial photographic archives.

## Dataset composition

| Source | Collection | # pictures |
| --- | --- | --- |
| Imperial War Museum (IWM) | Batch 1 | 199 |
| Universiteit Leiden | Nederlands-Indië in foto’s, 1860-1940 (ULNI) | 1981 |
| **Total** | | 2180 |

## Annotation
The annotation was carried out on Label Studio and comprises **three different classes**: sensitive, not-sensitive, dubious.

## Sensitive content definition
Before proceeding with the annotation of the data, it was necessary to outline a possible definition of "sensitive content" in the specific context of this project. Given the aim of the research, this definition mainly considers the mere content of the images, without examining the metadata attached.

A possible taxonomy of different varieties of sensitive content was produced as a result of the (ongoing) discussions on the material available and on previous research conducted on the matter (e.g. [National Research Council. 2004. Measuring Racial Discrimination](https://nap.nationalacademies.org/read/10887/chapter/1)), which was adapted to our specific historical scope:

```
sensitive content
|
├── explicit violence / abuse
|
├── scientific racism
│   └── physical anthropology
|
├── otherness
|   └── exoticism (fetishization)
|
└── exclusion / segregation
    ├── statistical (stereotypical representation)
    └── structural (hierarchical structure)
```

## Finetuning
The finetuning of pre-trained ML models (e.g., ViT, ResNet) is carried out using the 🤗Hugging Face `transformers` library.
