---
title: Understand the predictive opportunity scoring configuration page
description: Learn about the various sections in the predictive opportunity scoring configuration page in Dynamics 365 Sales.
ms.date: 11/06/2024
ms.custom: 
ms.topic: article
author: lavanyakr01
ms.author: lavanyakr
ms.reviewer: lavanyakr
---

# Understand the predictive opportunity scoring configuration page  

The **Predictive opportunity scoring** page is where you'll create, edit, publish, and delete opportunity scoring models. It's organized into the following sections:

- [Select a model](#select-a-model)
- [Actions you can perform on the model](#actions-you-can-perform-on-the-model)
- [Version details](#version-details)
- [Opportunity score grading](#opportunity-score-grading)
- [MultiModel](#multimodel)

:::image type="content" source="media/si-admin-predictive-opportunity-scoring-configuration-page.png" alt-text="Screenshot of the Predictive opportunity scoring page.":::

## License and role requirements

| Requirement type | You must have |
|-----------------------|---------|
| **License** | Dynamics 365 Sales Premium or Dynamics 365 Sales Enterprise<br>More information: [Dynamics 365 Sales pricing](https://dynamics.microsoft.com/sales/pricing/) |
| **Security roles** | System Administrator<br>More information: [Predefined security roles for Sales](security-roles-for-sales.md) |

## Select a model

If you've created two or more scoring models, use the **Select Model** list to select one of them to view, edit, or delete. The list contains both published and unpublished models. The list control doesn't appear if you have one or zero models.

:::image type="content" source="media/si-admin-predictive-opportunity-scoring-select-model-drop-down.png" alt-text="Screenshot of the Select Model list control on the Predictive opportunity scoring page.":::

## Actions you can perform on the model

- **Publish**: Publish a model so sellers in your organization can access the My Open Opportunities Scored system view and the Opportunity score widget on opportunity forms. After you publish a model, this button appears dimmed and is available only after you retrain or edit the model.

- **Edit model**: Update or add fields that affect the prediction accuracy score. [Edit and retrain a model](pos-edit-and-retrain-model.md#edit-and-retrain-an-opportunity-scoring-model) when you want to change the fields to consider or include a unique business process.

- **Revert version**: Return a retrained model to its previous version when it isn't satisfactory or doesn't meet your organization's requirements. This action is only available when you've retrained a model but haven't published it yet.

- **Delete model**: [Delete a model](pos-duplicate-models.md#delete-a-model) your organization no longer requires or that duplicates another model. This button is only available for published models.

:::image type="content" source="media/si-admin-predictive-lead-scoring-buttons.png" alt-text="Screenshot of model action buttons on the Predictive opportunity scoring page.":::

## Version details

This section shows information about the model's status and performance.

:::image type="content" source="media/si-admin-predictive-opportunity-scoring-version-details.png" alt-text="Screenshot of version details for an opportunity scoring model.":::

| Parameter | Description |
|-----------|-------------|
| Version trained on | The date the model was last trained. |
| Status | Whether the model is active or inactive. |
| Attributes used | The number of attributes that were used to train the model out of the total number of attributes available. If you're not satisfied with the outcome of the trained model, you can select **Retrain with recommended fields** to retrain the model with the standard (out-of-the-box) attributes. **Edited** appears next to the number if the attributes were custom-selected. |
| Model performance | The model's accuracy and projected performance are based on the data available and selected to train the model.<br>**Note**: The range of the accuracy score is defined based on the area under the curve (AUC) metric.<br>- **Ready to publish** indicates the model's accuracy is above the range, and you can expect the model will perform well.<br>- **OK to publish** indicates the model accuracy is within range, and you can expect the model might perform reasonably well.<br>- **Not ready to publish** indicates the model's accuracy is below the range, and you can expect the model will perform poorly. |
| Business process flow | The business process flow that's applied on the opportunities that are scored by this model. |
| Filter column and filter values | Which column and which values correspond to the opportunities that this specific model should score when you have multiple models. |
| State option set | The option set that's used for won and lost opportunities in this model. |
| Retrain automatically | Sets the model to be [automatically retrained](pls-edit-and-retrain-model.md#automatic-retraining) every 15 days. |
| Most influential fields | The top five attributes that most affect the outcome of the prediction accuracy score. |

## Opportunity score grading

When you publish a model, it grades the opportunities that are in your organization's pipeline according to the range defined in this section. Each opportunity in the pipeline is graded A, B, C, or D, according to the opportunity score. Opportunities in the top score range are graded A while opportunities in the lowest score range are graded D.

:::image type="content" source="media/si-admin-predictive-opportunity-scoring-grading.png" alt-text="Screenshot of opportunity score grades.":::

You can configure the grading range according to your organizational requirements. When you change the opportunity score range for a grade, the maximum range value for the adjacent grade changes automatically in accordance with the change in the minimum value. For example, if you change the minimum range value score for **Grade A** to 51, the maximum opportunity score range for **Grade B** changes to 50.

## MultiModel

Select **Add model** to [create a model](configure-predictive-opportunity-scoring.md#add-a-model) for a line of business that might use different opportunities than your first model. The **Add model** command is disabled when you reach the maximum limit of 10 models (both published and unpublished).

[!INCLUDE[cant-find-option](../includes/cant-find-option.md)]