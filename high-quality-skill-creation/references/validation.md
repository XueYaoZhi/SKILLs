# Behavioral Validation

Select realistic requests before deciding which resources are necessary. Do not merely check whether outputs contain prescribed headings.

| Scenario | Expected observation |
| --- | --- |
| User specifies the purpose and destination of a simple skill | Deliver a usable entrypoint without asking for the destination again or creating unnecessary directories |
| User requests only a broken-link fix | Correct the path without rewriting the workflow |
| Ordinary business document writing | Do not trigger skill creation |
| Target environment lacks an example tool | Use an available tool or accurately explain the limitation |
| Publication already has explicit authorization | Do not ask again; still verify the target and result |
| A referenced resource is missing | Do not claim to have read it; fix the reference or disclose the gap |

For complex skills, independent evaluation in an isolated workspace may help when authorized. Never operate production services merely to test a skill without authorization. Compare task outcomes with and without the skill, recording correctness, omissions, unnecessary interaction, and cost. Do not reveal expected conclusions to the evaluator through test materials.

Formatting checks do not prove that these behaviors occurred. Report scenarios actually executed, their results, and uncovered areas. Reference examples are not executed tests.
