# Personal Python Style preference

## Python Version and Standard
1. Use latest python (3.13) syntax.
2. do not import and use `from typing import Dict, List, Set` use native `list, dict, set` instead

## class and function Documentation
Use single-line (high level description) docstrings for classes, document classes and their field using pydantic BaseModel and Field(description=...), and rely on type hints. Avoid verbose docstrings that include Args, Returns, and similar sections.
- Good Example (follow this pattern):
```python
from pydantic import BaseModel, Field
import numpy as np

class ContrastiveExample(BaseModel):
    """Input triplet for contrastive learning."""
    anchor: np.ndarray = Field(..., description="Anchor vector")
    positive: np.ndarray = Field(..., description="Similar to anchor")
    negative: np.ndarray = Field(..., description="Dissimilar to anchor")
```
- Bad Example (avoid this pattern):
```python
class ContrastiveExample:
"""
This class represents a contrastive learning input sample.

Args:
  anchor (np.ndarray): The anchor vector.
  positive (np.ndarray): The positive sample, similar to the anchor.
  negative (np.ndarray): The negative sample, dissimilar to the anchor.

Returns:
  None

Raises:
  ValueError: If input shapes do not match.
"""

def __init__(self, anchor, positive, negative):
  self.anchor = anchor
  self.positive = positive
  self.negative = negative
```
   
