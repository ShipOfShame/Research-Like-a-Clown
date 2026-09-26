# Pattern catalog

This catalog abstracts the attached review records, not an author persona. Read the linked evidence records before selecting a pattern. Their versions, conditions, and attribution limits are part of the pattern scope. A source record is a historical observation, not a statement about the latest release.

| ID | Pattern | Evidence |
| --- | --- | --- |
| P01 | [availability-claim-gap](#p01-availability-claim-gap) | E01, E09, E11, E31 |
| P02 | [invalid-aggregate](#p02-invalid-aggregate) | E02, E30 |
| P03 | [metric-semantic-switch](#p03-metric-semantic-switch) | E03, E07 |
| P04 | [masked-candidate-exhaustion](#p04-masked-candidate-exhaustion) | E04 |
| P05 | [broken-release-dependency](#p05-broken-release-dependency) | E05, E13 |
| P06 | [opposite-update-sign](#p06-opposite-update-sign) | E06 |
| P07 | [conflicting-counts-or-timings](#p07-conflicting-counts-or-timings) | E08 |
| P08 | [evaluation-input-overlap](#p08-evaluation-input-overlap) | E10 |
| P09 | [validation-from-training](#p09-validation-from-training) | E12 |
| P10 | [supervised-selection-before-split](#p10-supervised-selection-before-split) | E13 |
| P11 | [feedback-not-delivered](#p11-feedback-not-delivered) | E14 |
| P12 | [different-transcripts-per-metric](#p12-different-transcripts-per-metric) | E15 |
| P13 | [normalization-erases-errors](#p13-normalization-erases-errors) | E16 |
| P14 | [algorithm-code-divergence](#p14-algorithm-code-divergence) | E17 |
| P15 | [overgeneralized-method-category](#p15-overgeneralized-method-category) | E18 |
| P16 | [identity-state-transition](#p16-identity-state-transition) | E19 |
| P17 | [incompatible-function-domains](#p17-incompatible-function-domains) | E20 |
| P18 | [metaphor-as-taxonomy](#p18-metaphor-as-taxonomy) | E21 |
| P19 | [score-assigned-to-wrong-condition](#p19-score-assigned-to-wrong-condition) | E22 |
| P20 | [test-guided-selection](#p20-test-guided-selection) | E23 |
| P21 | [unused-experimental-parameter](#p21-unused-experimental-parameter) | E24 |
| P22 | [different-events-in-ratio](#p22-different-events-in-ratio) | E25 |
| P23 | [wrong-metric-denominator](#p23-wrong-metric-denominator) | E26 |
| P24 | [signed-probability-path](#p24-signed-probability-path) | E27 |
| P25 | [judge-without-reference](#p25-judge-without-reference) | E28 |
| P26 | [unexecuted-revision-provenance](#p26-unexecuted-revision-provenance) | E29 |
| P27 | [vocabulary-as-sequence-space](#p27-vocabulary-as-sequence-space) | E32 |
| P28 | [inconsistent-model-identifier](#p28-inconsistent-model-identifier) | E33 |

## P01 availability-claim-gap

**Generate:** Describe an implementation or original research material as available while the accompanying fictional release inventory lacks it, contains only part of it, or points to an expired resource. Match the selected source subtype: missing code, missing original annotations, pending preprocessing/configuration, or expired access.

**Construction constraint:** Pair an availability paragraph with a short release inventory; do not turn a partial release into a claim that nothing was released.

**Evidence:** E01, E09, E11, E31 in [evidence.json](evidence.json).

- E01: Teaching Time Series to See and Speak: Forecasting with Aligned Visual and Textual Perspectives — Code availability statement does not match the repository contents
  - Source: https://github.com/Ironieser/TimesCLIP/tree/269fc3057068aecd4d89055b7cb48025d3a012e2
  - Scope: An author replied on July 22, 2025 that code and models would be released after formal acceptance. Acceptance status was not established, so this record does not claim that deadline was breached or that the authors never replied. It does not establish fabrication or assign the omission to an individual coauthor.

- E09: MLLM-Tool: A Multimodal Large Language Model For Tool Agent Learning — Complete original model cards were not released
  - Source: https://github.com/Chenyu-Wang567/MLLM-Tool/issues/6#issuecomment-3390754375
  - Scope: Code and some data are public; issue #7 also contains a response identifying test materials. The disclosed restrictions may have legitimate reasons. This record does not claim that all data are unavailable, that a specific venue rule was breached, or that the data were fabricated.

- E11: RoomDesigner: Encoding Anchor-latents for Style-consistent and Shape-compatible Indoor Scene Generation — Some configurations and data-processing code remain pending
  - Source: https://github.com/zhao-yiqun/RoomDesigner/blob/3980e06bfc48f76f3f1efb2d2182c0c871d2231b/README.md#L45
  - Scope: Model code is available. In issue #2 the author says vqvae_model_texture is not used in the framework; this record does not treat that reported import concern as a proven runtime blocker. The evidence does not establish deliberate withholding or a venue-policy violation.

- E31: LLM-ML Teaming: Integrated Symbolic Decoding and Gradient Search for Valid and Stable Generative Feature Transformation — The code repository linked in the abstract has expired
  - Source: https://anonymous.4open.science/r/LLM-ML-Teaming-DCAI-B391
  - Scope: The reviewed manuscript is arXiv 2506.09085v1.

## P02 invalid-aggregate

**Generate:** Give component measurements or subgroup sizes and means, then report an aggregate inconsistent with their arithmetic. Preserve the distinction between a sum mislabeled as a mean and an incompatible weighted mean.

**Construction constraint:** Use a small constructed table whose inconsistency can be checked arithmetically; do not claim its values are measured.

**Evidence:** E02, E30 in [evidence.json](evidence.json).

- E02: Teaching Time Series to See and Speak: Forecasting with Aligned Visual and Textual Perspectives — The PEMS07 Avg row is inconsistent with its four component values
  - Source: https://arxiv.org/abs/2506.24124v2
  - Scope: The aggregate values are close to sums rather than means; other methods show a similar pattern. A shared scaling error could leave the within-dataset ranking unchanged. The table inconsistency does not demonstrate that the component results were invented.

- E30: TransRAC: Encoding Multi-scale Temporal Correlation with Transformers for Repetitive Action Counting — RepCount combined statistics conflict with the reported subsets
  - Source: https://arxiv.org/html/2204.01018v1#S3
  - Scope: The arithmetic checks the printed summary statistics; raw video annotations were not recomputed.

## P03 metric-semantic-switch

**Generate:** Report one quantity using the name of another: retained relative performance as absolute performance, or question-level accuracy as case-level accuracy.

**Construction constraint:** Supply enough surrounding definitions to make the change of meaning observable, rather than merely omitting a definition.

**Evidence:** E03, E07 in [evidence.json](evidence.json).

- E03: MMTok: Multimodal Coverage Maximization for Efficient Inference of VLMs — README and paper report inconsistent performance metrics
  - Source: https://github.com/Ironieser/MMTok/blob/8e2686836ed5bbe05d064f1d1c20e50c73c70b94/README.md
  - Scope: The final OpenReview PDF was not obtained. The finding concerns the pinned README and arXiv v2, not every paper version. It establishes inconsistent reporting, not fabricated measurements.

- E07: LogicIF: Towards Complex Logic Instruction Following — Figure 6 inconsistently labels the accuracy metric
  - Source: https://arxiv.org/abs/2508.09125v4
  - Scope: The evidence supports a caption/metric-label error, not a claim that the plotted numbers were fabricated. The v4 PDF labels itself COLM 2026; the final venue archive was not independently obtained.

## P04 masked-candidate-exhaustion

**Generate:** Describe selection up to the total input count while excluding some inputs; after exhausting eligible candidates, continue selecting from entirely masked scores.

**Construction constraint:** Include selection pseudocode and an input with fewer eligible items than the budget. Preserve the conditional nature of the failure.

**Evidence:** E04 in [evidence.json](evidence.json).

- E04: MMTok: Multimodal Coverage Maximization for Efficient Inference of VLMs — Padding exclusion can exhaust valid tokens and repeatedly select a masked token
  - Source: https://github.com/Ironieser/MMTok/blob/8e2686836ed5bbe05d064f1d1c20e50c73c70b94/mmtok/core/semantic_selector.py#L43-L64
  - Scope: The result follows from the padding arithmetic and loop control flow. The frequency of this input condition in the paper benchmarks was not measured.

## P05 broken-release-dependency

**Generate:** Pair a runnable-entry claim with an accompanying code excerpt whose import chain contains either a syntax error or an unavailable required module.

**Construction constraint:** Choose one documented subtype; never break existing user code or install dependencies to demonstrate it.

**Evidence:** E05, E13 in [evidence.json](evidence.json).

- E05: Brownian Bridge Augmented Surrogate Simulation and Injection Planning for Geological CO2 Storage — A module imported by the public entry point contains an indentation error
  - Source: https://github.com/HaoyueBai98/Brownian_Bridge_Augmented_CO2_Storage/blob/2616f119eadd2873755b58292b9d5768f30d0b6d/loaders/simdec_loader.py#L58
  - Scope: Only source text was parsed; no research code, model, or experiment was executed. A release-time editing error is possible. This does not establish that the authors used this snapshot for the paper or never ran the experiments.

- E13: Sculpting Features from Noise: Reward-Guided Hierarchical Diffusion for Task-Optimal Feature Transformation — Missing imported module and supervised feature selection before splitting
  - Source: https://github.com/NanxuGong/DIFFT/tree/a8461c664d91704c56a91c130c95910be1aef327
  - Scope: No research code was executed. Existing caches bypass the described selection branch; the caches and code used for the publication were not established. The finding documents release defects and a conditional leakage path, not proven contamination of the paper tables or absence of a review-time supplement.

## P06 opposite-update-sign

**Generate:** Define one signed loss and give an equation that adds its gradient, while paired implementation pseudocode subtracts the same gradient.

**Construction constraint:** Hold the loss definition fixed so that the mismatch is a sign change, not a different optimization convention.

**Evidence:** E06 in [evidence.json](evidence.json).

- E06: Efficient Post-Training Refinement of Latent Reasoning in Large Language Models — The equation and public code use opposite update signs
  - Source: https://github.com/anord-wang/Lateng-Reasoning/blob/94e70c46acb39c45c713d010d53f9e06421527d8/coconut_search.py#L74
  - Scope: This identifies a paper/code specification mismatch; it does not establish which rule generated the reported results. The code refines embeddings without updating model parameters. No fabrication or individual intent is inferred.

## P07 conflicting-counts-or-timings

**Generate:** Make category counts fail to sum to their stated total, or give incompatible timing accounts for the same named example under the same conditions.

**Construction constraint:** Use internally constructed numbers. Do not infer that a small count discrepancy reverses a conclusion.

**Evidence:** E08 in [evidence.json](evidence.json).

- E08: Rethinking Model Efficiency: Multi-Agent Inference with Large Models — Routing counts and timings for the same example are inconsistent
  - Source: https://arxiv.org/html/2604.04929v1
  - Scope: The one-case count difference is about 0.023%; its effect on conclusions is unresolved. Both timing accounts suggest a speedup, but with different magnitudes. The paper separately discloses estimates and measured timings, so this does not imply that all latency claims are unmeasured or false.

## P08 evaluation-input-overlap

**Generate:** Describe an independent held-out evaluation while paired split records repeat training inputs in the evaluation set, optionally with overlapping accepted answers.

**Construction constraint:** Provide miniature split records. For media paths, retain the distinction between matching references and verified byte equality.

**Evidence:** E10 in [evidence.json](evidence.json).

- E10: MLLM-Tool: A Multimodal Large Language Model For Tool Agent Learning — The released test set contains 184 inputs already present in training
  - Source: https://github.com/ShipOfShame/Academic-Misconduct-Marker/blob/main/evidence-database/analyses/mllmtool-overlap-20260926.json
  - Scope: Media equality is established at the path-reference level. The counts describe the released split; the effect on reported model accuracy was not measured.

## P09 validation-from-training

**Generate:** Describe checkpoint selection on held-out validation data while the loader takes validation examples from the training list.

**Construction constraint:** Pair the evaluation description with a miniature loader; keep the scope to the affected component.

**Evidence:** E12 in [evidence.json](evidence.json).

- E12: RoomDesigner: Encoding Anchor-latents for Style-consistent and Shape-compatible Indoor Scene Generation — Shape-encoder validation reuses the first five training objects
  - Source: https://github.com/zhao-yiqun/RoomDesigner/blob/3980e06bfc48f76f3f1efb2d2182c0c871d2231b/3DILG/FRONT.py#L302-L387
  - Scope: This is the public shape-encoder training path, separate from the room-level scene-generation test split and its reported FID/SCA results.

## P10 supervised-selection-before-split

**Generate:** Fit label-dependent feature selection on all rows before splitting into training and test sets, while describing the test split as independent.

**Construction constraint:** Use the uncached branch explicitly; do not infer that cached or unexamined publication runs took it.

**Evidence:** E13 in [evidence.json](evidence.json).

- E13: Sculpting Features from Noise: Reward-Guided Hierarchical Diffusion for Task-Optimal Feature Transformation — Missing imported module and supervised feature selection before splitting
  - Source: https://github.com/NanxuGong/DIFFT/tree/a8461c664d91704c56a91c130c95910be1aef327
  - Scope: No research code was executed. Existing caches bypass the described selection branch; the caches and code used for the publication were not established. The finding documents release defects and a conditional leakage path, not proven contamination of the paper tables or absence of a review-time supplement.

## P11 feedback-not-delivered

**Generate:** Describe a critic using accumulated iteration feedback while appending history to one variable and sending only the initial prompt in the actual call.

**Construction constraint:** Show both the update and call payload so the missing connection is visible; preserve any separate generator history.

**Evidence:** E14 in [evidence.json](evidence.json).

- E14: Unsupervised Feature Transformation via In-context Generation, Generator-critic LLM Agents, and Duet-play Teaming — The critic does not receive the accumulated iteration feedback
  - Source: https://github.com/NanxuGong/LPFG/blob/6bc2be0dcd639600123f826f687288d164f3f975/LPFG.py#L253
  - Scope: The generator retains its own context, so this is not a claim that all iteration is absent. The review did not establish that this released commit produced the publication results. No API calls or model runs were made.

## P12 different-transcripts-per-metric

**Generate:** Present metrics as evaluating one output while one evaluator applies a text transformation and the others reload the original text.

**Construction constraint:** Include a short evaluation-flow description with both transcript versions.

**Evidence:** E15 in [evidence.json](evidence.json).

- E15: Towards Robust Dysarthric Speech Recognition: LLM-Agent Post-ASR Correction Beyond WER — WER and semantic metrics evaluate different transcript versions
  - Source: https://github.com/xiuwenz2/SAP-Hypo5/blob/5d37b96fd25a3e612ba9a4c04d44de4446f5d3fe/evaluate.sh#L43
  - Scope: Static result for the published evaluation entry and its invoked scripts.

## P13 normalization-erases-errors

**Generate:** Delete digits from both reference and prediction before scoring, while treating the resulting score as covering numerical correctness.

**Construction constraint:** Use a harmless constructed example such as room 12 versus room 13. The collapse follows from normalization, not a measured dataset effect.

**Evidence:** E16 in [evidence.json](evidence.json).

- E16: Towards Robust Dysarthric Speech Recognition: LLM-Agent Post-ASR Correction Beyond WER — Digit deletion removes numerical errors before scoring
  - Source: https://github.com/xiuwenz2/SAP-Hypo5/blob/5d37b96fd25a3e612ba9a4c04d44de4446f5d3fe/inference.py#L31
  - Scope: This is a constructed static counterexample; the incidence and score impact on actual samples were not measured.

## P14 algorithm-code-divergence

**Generate:** Specify truncation at the first selected repeated phrase, but pair it with pseudocode that compresses repeats selectively and keeps later content.

**Construction constraint:** Include a short repeated sequence that distinguishes the two operations.

**Evidence:** E17 in [evidence.json](evidence.json).

- E17: Towards Robust Dysarthric Speech Recognition: LLM-Agent Post-ASR Correction Beyond WER — Released repetition handling differs from Algorithm 1
  - Source: https://arxiv.org/html/2601.21347v1
  - Scope: Comparison of the published pseudocode and this fixed implementation.

## P15 overgeneralized-method-category

**Generate:** Characterize an entire generative-search category as continuous even though an included method searches discrete operations with tree search.

**Construction constraint:** Use abstract fictional methods and make the category member explicit; do not invent a published citation.

**Evidence:** E18 in [evidence.json](evidence.json).

- E18: A Survey on Data-Centric AI: Tabular Learning from Reinforcement Learning and Generative AI Perspective — The continuous-search characterization excludes a cited generative method
  - Source: https://arxiv.org/html/2502.08828v2#S7
  - Scope: The counterexample is present in the cited paper v1 from 2024, before this survey v2.

## P16 identity-state-transition

**Generate:** Describe feature removal through a next-state equation S_next = S union A, where A is a subset of S.

**Construction constraint:** Include the subset condition; it makes the transition equal to S for every allowed action.

**Evidence:** E19 in [evidence.json](evidence.json).

- E19: Toward Data-Centric AI: A Comprehensive Survey of Traditional, Reinforcement, and Generative Approaches for Tabular Data Transformation — The feature-selection state transition always returns the original set
  - Source: https://doi.org/10.1145/3801742
  - Scope: Survey formalization in the published version; the same expression occurs in arXiv v1.

## P17 incompatible-function-domains

**Generate:** Define a decoder from embeddings to sequences and an evaluator from embeddings to scores, then compose evaluator(decoder(e)) without a conversion.

**Construction constraint:** State all domains explicitly so the composition mismatch is recoverable.

**Evidence:** E20 in [evidence.json](evidence.json).

- E20: Toward Data-Centric AI: A Comprehensive Survey of Traditional, Reinforcement, and Generative Approaches for Tabular Data Transformation — The generative objective composes functions with incompatible domains
  - Source: https://doi.org/10.1145/3801742
  - Scope: Mathematical definitions in the published survey, also present in arXiv v1.

## P18 metaphor-as-taxonomy

**Generate:** Classify a population search method with a tree-growth metaphor as an embedded predictive-tree feature selector.

**Construction constraint:** Describe the actual population/vector mechanism alongside the incompatible category; retain the distinction between representation and predictive model.

**Evidence:** E21 in [evidence.json](evidence.json).

- E21: Toward Data-Centric AI: A Comprehensive Survey of Traditional, Reinforcement, and Generative Approaches for Tabular Data Transformation — iTGA natural-growth search is classified as embedded tree-model selection
  - Source: https://doi.org/10.1145/3801742
  - Scope: Reference 208 was checked against the primary article; this finding concerns that specific classification.

## P19 score-assigned-to-wrong-condition

**Generate:** Place a score under one task condition in a table and attribute that score to a different condition in the prose.

**Construction constraint:** Make both condition labels explicit and keep table and prose within the same constructed version.

**Evidence:** E22 in [evidence.json](evidence.json).

- E22: To Think or Not To Think, That is The Question for Large Reasoning Models in Theory of Mind Tasks — An Order 0 accuracy is described as an Order 1 result
  - Source: https://arxiv.org/html/2602.10625v3#A3.SS1.SSS1
  - Scope: Comparison within arXiv v3.

## P20 test-guided-selection

**Generate:** Describe a final independent test evaluation while using test labels to rank candidates and trigger early stopping throughout optimization.

**Construction constraint:** Show the selection and stop rules; the original repository-to-paper attribution remains qualified in the source record.

**Evidence:** E23 in [evidence.json](evidence.json).

- E23: Bridging the Domain Gap in Equation Distillation with Reinforcement Feedback — Test labels enter equation selection and early stopping
  - Source: https://github.com/yingwangyang/Data2Eqn-RL/blob/4e27dd98f011963511cda60af4caadbfdc24e755/finetune_e2e.py#L233
  - Scope: Repository attribution is inferred from the first-author account and matching method details. The paper does not link this repository; the finding applies to this commit.

## P21 unused-experimental-parameter

**Generate:** Describe a parameter-controlled noise experiment while constructing noise but storing the original labels unchanged.

**Construction constraint:** Include the data-write step. Do not invent observed robustness results.

**Evidence:** E24 in [evidence.json](evidence.json).

- E24: Bridging the Domain Gap in Equation Distillation with Reinforcement Feedback — The target_noise parameter does not change training labels
  - Source: https://github.com/yingwangyang/Data2Eqn-RL/blob/4e27dd98f011963511cda60af4caadbfdc24e755/finetune_data.py#L29
  - Scope: Repository attribution is inferred from the first-author account and matching method details. The paper does not link this repository; the finding applies to this commit.

## P22 different-events-in-ratio

**Generate:** Describe a policy probability ratio at the same state/action, but use separately generated trajectories and divide their own chosen-action probabilities; optionally align KL by position across different prefixes.

**Construction constraint:** Make the distinct prefixes or actions visible and retain the common-event requirement in the claimed formula.

**Evidence:** E25 in [evidence.json](evidence.json).

- E25: Bridging the Domain Gap in Equation Distillation with Reinforcement Feedback — Probability ratios and KL compare separately generated trajectories
  - Source: https://github.com/yingwangyang/Data2Eqn-RL/blob/4e27dd98f011963511cda60af4caadbfdc24e755/finetune_e2e.py#L153
  - Scope: Repository attribution is inferred from the first-author account and matching method details. The paper does not link this repository; the finding applies to this commit.

## P23 wrong-metric-denominator

**Generate:** Define explained variance using the ground-truth total sum of squares in one place and prediction variation in another.

**Construction constraint:** Use a symbolic formula or a constructed two-point example, not an invented empirical result.

**Evidence:** E26 in [evidence.json](evidence.json).

- E26: Bridging the Domain Gap in Equation Distillation with Reinforcement Feedback — The experimental R-squared denominator uses predictions
  - Source: https://arxiv.org/html/2505.15572v1#S4.SS1
  - Scope: The related repository calls r2_score with true and predicted labels; this finding concerns the printed formula.

## P24 signed-probability-path

**Generate:** Treat signed similarities as multiplicative emission probabilities while forbidden transitions receive zero, allowing a zero-valued forbidden path to beat negative allowed paths.

**Construction constraint:** Include a two-step illustrative recurrence. Keep this scoped to the Viterbi option, not the default sorting path.

**Evidence:** E27 in [evidence.json](evidence.json).

- E27: Weakly Supervised Video Representation Learning with Unaligned Text for Sequential Videos — Signed similarities let the Viterbi branch return a backward label path
  - Source: https://github.com/svip-lab/WeakSVR/blob/0caa9eb05ff77f8798167a8ad754e90f3a059af2/utils/loss.py#L73-L101
  - Scope: The counterexample is derived from the Viterbi option. The default command-line option is sorting.

## P25 judge-without-reference

**Generate:** Describe visual identity comparison against reference images while the judge payload contains only generated imagery and a text flag saying references exist.

**Construction constraint:** Show the actual payload separately from the generator inputs; text mentioning an image does not attach it.

**Evidence:** E28 in [evidence.json](evidence.json).

- E28: Better Call CineCrew: Consistent Ultra-Long Narrative-to-Film Generation — The visual judge is asked to compare identity without the reference images
  - Source: https://github.com/Ironieser/CineCrew/blob/9a00efa7db65ba028c1523907f6cee844776123a/src/agents/production_operator/production_operator_agent.py#L232-L266
  - Scope: This finding concerns the production visual judge and its message payload.

## P26 unexecuted-revision-provenance

**Generate:** On the final rejected attempt, revise a prompt without regenerating the output, then store that new prompt as the provenance of the previous output.

**Construction constraint:** Use symbolic prompts P0/P1 and artifact I0; the mismatch requires a final rejection and a nonempty revision.

**Evidence:** E29 in [evidence.json](evidence.json).

- E29: Better Call CineCrew: Consistent Ultra-Long Narrative-to-Film Generation — A final rejection can associate media with an unexecuted revised prompt
  - Source: https://github.com/Ironieser/CineCrew/blob/9a00efa7db65ba028c1523907f6cee844776123a/src/agents/production_operator/production_operator_agent.py#L244-L285
  - Scope: The path requires a final rejected attempt with a nonempty revised_prompt; it is established by static control-flow analysis.

## P27 vocabulary-as-sequence-space

**Generate:** Count available tokens and present that vocabulary size as the number of complete expressions, then claim a notation change eliminates exponential search.

**Construction constraint:** State the token set and permitted sequence construction so the distinction can be inspected.

**Evidence:** E32 in [evidence.json](evidence.json).

- E32: LLM-ML Teaming: Integrated Symbolic Decoding and Gradient Search for Valid and Stable Generative Feature Transformation — The postfix search-space claim confuses token vocabulary with complete sequences
  - Source: https://arxiv.org/html/2506.09085v1#A1
  - Scope: The reviewed manuscript is arXiv 2506.09085v1.

## P28 inconsistent-model-identifier

**Generate:** Combine the release-version label of one model with a size belonging to another release and present the combination as a single checkpoint identifier.

**Construction constraint:** Use an explicitly user-supplied or fictional release inventory; do not fabricate an official model release or performance measurement.

**Evidence:** E33 in [evidence.json](evidence.json).

- E33: LLM-ML Teaming: Integrated Symbolic Decoding and Gradient Search for Valid and Stable Generative Feature Transformation — Table 6 identifies a teacher model as LLaMA 3.2-405B
  - Source: https://arxiv.org/html/2506.09085v1#A8.T6
  - Scope: The reviewed manuscript is arXiv 2506.09085v1.
