# Ball Pipeline
Special object that allows a ball, either wood or iron, to transition from one layer to another. The pipeline can be rotated to decide whether the ball is moved one layer inwards or one layer outwards.

When a ball rolls inside the pipeline, the pipeline will enclose the ball within a box and begin the pipeline shift. The pipeline will wait until there is no other object in the way. As soon as the target layer is free from other objects in the target location, the ball is immediately pushed to that layer. The pipeline then opens itself up again and allows for the next ball to enter the process.

## User Information