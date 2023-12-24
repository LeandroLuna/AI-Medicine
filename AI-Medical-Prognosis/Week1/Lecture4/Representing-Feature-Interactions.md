# Risk Score Computation

In the "Risk Score Computation" lesson, the instructor formalizes the computation of scores in prognostic models, building upon examples previously discussed. The key points covered in the lesson are as follows:

- **Risk Equation:**
   - The computation of risk scores in prognostic models is formalized as a risk equation. This equation expresses the score as the sum of each feature multiplied by the coefficient associated with that feature. The overall score is obtained by summing up these contributions.

- **Linearity and Transformation:**
   - The risk equation does not necessarily need to be linear in the features themselves. It can be linear in the natural log or log base 10 of the features, as demonstrated in the MELD score example.

- **Interaction Terms:**
   - Interaction terms are introduced and discussed. Interaction terms involve the multiplication of two features and are further multiplied by a coefficient associated with the product. The ASCVD risk example is referenced to illustrate the use of interaction terms.

- **Understanding Interaction Terms:**
   - The lesson explores the impact of interaction terms graphically. Without interaction terms, the relationship between variables is independent. With interaction terms, the relationship between variables can depend on other factors. An example involving the natural log of age and the natural log of blood pressure is used to demonstrate how interaction terms capture dependence between variables. The effect of blood pressure on risk may vary based on the value of another variable, such as age.

- **Evaluation of Prognostic Models:**
   - The lesson concludes by hinting at the next topic—how to evaluate a prognostic model.

In summary, the lesson provides a formal understanding of risk equations, explores linearity and transformation, introduces interaction terms, and illustrates their impact on capturing dependencies between variables in prognostic models.