# Structure Before Meaning

**Giving a cognitive substrate sight: structure is perceived by algorithm, meaning is learned by the
substrate, and vision is built as a single faculty.**

Stefan Ragland, Dominion Labs Research & Development. Published 20 May 2025.

- Paper (PDF): [`paper/structure-before-meaning.pdf`](paper/structure-before-meaning.pdf)
- Paper (web): <https://dmnlabs.org/research/structure-before-meaning/>
- Contact: research@dmnlabs.org

## The position

Vision is usually bought whole: pixels go into a network trained on millions of labelled pictures and
names come out. This paper argues that seeing is two acts rather than one. Recovering the structure of an
image, meaning where the coherent things are and how big, what shape, what colour, and whether they move,
has been solved by algorithms for two decades with no learning at all. Attaching a name to a novel
category is the only part that genuinely requires a learner, and every recent training-free recogniser
supplies that learner as a pretrained backbone. The thesis is that a substrate which already learns
concepts by induction can be the learner itself, with no network anywhere in the loop, and that sight
should be built as a faculty with one entry point rather than as a pipeline bolted to the side.

## What has since been measured

The position makes claims that can be checked, and section 7 of the paper reports what the experiments
settled. The measurements are in `data/`, and the companion paper
([repository](https://github.com/DominionLabsInc/perceive-induce-name),
[paper](https://dmnlabs.org/research/perceive-induce-name/)) reports them in full.

| Claim | Measurement | Data |
|---|---|---|
| The structure side is solved without learning | shape class 100% and colour family 100% over 149 images, with the operating range under noise, blur, rotation, desaturation, occlusion and apparent size mapped | [`data/perceive-eval2.json`](data/perceive-eval2.json) |
| The substrate can supply the naming half | 95.8% mean naming recall over eight categories, taught from four labelled images each, with zero language model calls | [`data/perceive-eval2.json`](data/perceive-eval2.json) |
| It abstains rather than guessing | 100% abstention on held-out non-members and zero false namings, including where the examples admitted more than one hypothesis | [`data/perceive-ambig-01.json`](data/perceive-ambig-01.json) |
| Ambiguity is reported, not guessed away | naming only what every surviving hypothesis accepts gives zero false namings out of 192 non-members, where a permissive policy gives 26 | [`data/perceive-ambig-01.json`](data/perceive-ambig-01.json) |
| The substrate says what would settle it | the case it asks for closes the ambiguity in 16 of 16 inductions, against 1 of 16 for randomly chosen examples | [`data/perceive-ambig-02.json`](data/perceive-ambig-02.json) |

Each file is the manifest its run wrote, unedited. The stimuli for these studies, and a fuller data
dictionary, are in the companion repository.

## Citation

```bibtex
@techreport{ragland2025structure,
  title       = {Structure Before Meaning: giving a cognitive substrate sight},
  author      = {Ragland, Stefan},
  institution = {Dominion Labs},
  year        = {2025},
  month       = {5},
  url         = {https://dmnlabs.org/research/structure-before-meaning/}
}
```

## License

The paper and the data are released under [Creative Commons Attribution 4.0](LICENSE). Please cite the
paper if you use them.
