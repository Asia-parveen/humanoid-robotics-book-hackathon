# Answer Grounding Skill

## Purpose
Ensure AI-generated responses are strictly based on provided context or documentation, preventing hallucinations and maintaining factual accuracy. This skill validates that answers are properly grounded in source material.

## When to Use
- Processing queries against documentation sets
- Building RAG-based chatbots
- Generating responses for sensitive domains (legal, medical, technical)
- Validating AI output accuracy
- Creating fact-checked responses
- Educational content generation

## Inputs
- Source context/document
- User query or question
- Generated AI response
- Confidence thresholds
- Fact-checking requirements
- Citation preferences

## Outputs
- Grounded response validated against context
- Source citation references
- Confidence scores for grounded claims
- Unverified statement identification
- Context relevance assessment
- Accuracy validation report

## Constraints
- Only include information present in the provided context
- Flag any statements not supported by source material
- Maintain high precision over recall
- Prevent introduction of external knowledge
- Ensure citations are accurate and specific
- Reject responses that rely on hallucinated information
- Require explicit evidence for factual claims
- Maintain transparency about information sources