[Deployment Link](https://huggingface.co/spaces/gustana/Satellite_Image_Classification)

[Slides Link](https://www.canva.com/design/DAGSh9Z_Zz4/mUAqdR8An-Hzg4MQqiXngg/view?utm_content=DAGSh9Z_Zz4&utm_campaign=designshare&utm_medium=link&utm_source=editor)

# Background Problem
- Earth is currently the only planet on which humans and other creatures live. 
- Sadly, human activities worsen the Earth's condition over time through global warming. 
- To monitor earth's condition, scientists have been analyzing images that captured from artificial satellites.

# Objective
- To help scientist classify images that captured from satellite, I will create a deep learning model that can automate that process.
- Thus, they can focused on more important tasks.

# Modelling

## Model Architecture

|     Layer       |     Output Shape     |    Param    |
|  ------------   | :------------------- | :---------- |
|  Convolution 2D | (None, 64, 64, 128)  |  1,664      |
|  AVG Pooling 2D | (None, 32, 32, 128)  |  0          |
|  Convolution 2D | (None, 16, 16, 256)  |  131,328    |
|  Flatten        | (None, 65,536)       |  0          |
|  Dense          | (None, 512)          |  33,554,944 |
|  Dense          | (None, 4)            |  2,052      |

## Model Result

|                | Accuracy | Loss | Num. of Images |
|  ------------  | :------- | :--- | :------------- |
|  Training Set  |    89%   | 25%  |      4,280     |
| Validation Set |    93%   | 28%  |      1,070     |
|    Test Set    |    95%   |  -   |       281      |


# Conclusion

- This model able to achieve 95% accuracy across 4 classes.
- Which means, out of 100 images, this model correctly classify 95 of them

- Despite this model being able to meet the minimum requirement for accuracy, the validation curves for accuracy and loss are highly volatile.
- **Thus, 95% accuracy on unseen data can't be trusted blindly.**
- **The model can be improved by adding more images for training and validation sets**

# Deployment

This project has been deployed to hugging face using streamlit as UI.
Refer to this [link](https://huggingface.co/spaces/gustana/Satellite_Image_Classification) to open the deployed model.