<h1>Troubleshooting</h1>

<p>This section presents the different errors that can appear when using the library.</p>

<p>Code</p>

<p>VI</p>

<p>Information</p>

<p>5001</p>

<p>check_bidirectional_output</p>

<p>The layers sent in the “layer” and “backward_layer” parameters of the</p>

<p>Bidirectional</p>

<p>layer must have the same output shape, unless the value of the merge_mode parameter is “concat”. For layers to have the same output shape, the same value must be set in the “units” parameter (parameter of the layer sent to the bidirectional layer).</p>

<p>5002</p>

<p>check_bidirectional_return_sequences</p>

<p>The layers sent in the “layer” and “backward_layer” parameters of the</p>

<p>Bidirectional</p>

<p>layer must have the same value for the return_sequences parameter.</p>

<p>5003</p>

<p>check_conv</p>

<p>The convolution is not feasible because the shape of the input is not large enough.</p>

<p>You have three solutions:</p>

<ul>
<li>Enlarge the input size</li>
<li>Reduce the size of the kernel</li>
<li>Set the “padding” parameter of the layer to “same” (padding will be added in such a way as to convolve in all cases)</li>
</ul>

<p>5004 – 5026 – 5027</p>

<p>check_attention</p>

<p>The entries in the</p>

<p>Attention</p>

<p>layer do not have the correct input shape.</p>

<p>5004 – 5005 – 5026</p>

<p>check_additive_attention</p>

<p>The entries in the</p>

<p>AdditiveAttention</p>

<p>layer do not have the correct input shape.</p>

<p>5004 – 5026</p>

<p>check_multiheadattention</p>

<p>The entries in the</p>

<p>MultiHeadAttention</p>

<p>layer do not have the correct input shape.</p>

<p>5006</p>

<p>check_input_same_index</p>

<p>The index selected when formatting the data at the input of the forward is already defined.</p>

<p>5007</p>

<p>check_input_shape</p>

<p>The input layer does not exist. Add the</p>

<p>Input</p>

<p>layer at the beginning of the model or use the “in/out param” parameter of the layer that starts your model.</p>

<p>5008</p>

<p>check_nb_input</p>

<p>The number of inputs sent to the forward does not match the number of inputs in the model.</p>

<p>5009</p>

<p>check_nb_y_true</p>

<p>The number of outputs (y_true) sent to the loss does not correspond to the number of trainable outputs of the model.</p>

<p>Caution : if your forward is in training mode it will not allow loss, if you want metric loss, use metric functionalities.</p>

<p>5010</p>

<p>warning_input_shape</p>

<p>An input already exists, so the input shape you defined in the “in/out param” parameter is not taken into account.</p>

<p>5011</p>

<p>check_output_same_index</p>

<p>The index selected when formatting the data sent to the loss (y_true) is already defined.</p>

<p>5012</p>

<p>check_shape</p>

<p>The inputs of the operand (</p>

<p>Add</p>

<p>or</p>

<p>Average</p>

<p>or</p>

<p>Multiply</p>

<p>or</p>

<p>Substract</p>

<p>) do not have the same shape.</p>

<p>5013</p>

<p>check_shape_concat</p>

<p>The entries of the</p>

<p>Concatenate</p>

<p>layer do not have the same shape.</p>

<p>Note that the size of the axis on which we concatenate can be different.</p>

<p>Example: if we have an entry with shape (10, 2, 3), another with shape (10, 2, 4) and the parameter “axis” of the layer is 1, then the error occurs because when checking the shape, the layer considers that one entry has a shape of (10, 3) and the other one (10, 4). If “axis” is 2, then there is no error because during the verification of the shape, the layer considers that the entries have a shape of (10, 2).</p>

<p>5014</p>

<p>check_shape_set_input</p>

<p>The dimensions of the input array provided does not correspond to those expected.</p>

<p>5015</p>

<p>check_shape_set_weight</p>

<p>The dimensions of the weight array provided does not correspond to those expected.</p>

<p>5016</p>

<p>check_shape_y_true</p>

<p>The dimensions of the y_true array provided does not correspond to those expected.</p>

<p>5018</p>

<p>warning_output_index</p>

<p>The output order specified is out of bound (x &lt; 0 or x &gt; nb_output).</p>

<p>5019</p>

<p>warning_input_name</p>

<p>The layer name specified isn’t an input of model.</p>

<p>5020</p>

<p>check_output_same_name</p>

<p>The name specified when formatting the data sent to the loss (y_true) is already defined.</p>

<p>5021</p>

<p>warning_input_index</p>

<p>The input order specified is out of bound (x &lt; 0 or x &gt; nb_input).</p>

<p>5022</p>

<p>display_name_error</p>

<p>The name specified doesn’t exist in the graph.</p>

<p>5023 – 5039</p>

<p>check_gpu_layer</p>

<p>One or more layers are not available in CUDA version.</p>

<p>5024</p>

<p>display_dim_error</p>

<p>The layer does not support the given dimension.</p>

<p>5028</p>

<p>check_dim</p>

<p>The input is incompatible with the layer.</p>

<p>5029</p>

<p>check_dim</p>

<p>The product of the input form is not equal to the product of the output form.</p>

<p>Example: for an input shape (10, 2, 3, 5) the product is equal to 300 (10 * 2 * 3 * 5) then, in output if we want 3D we will have for example a shape of (10, 3, 10).</p>

<p>5030</p>

<p>check_graphs_shape</p>

<p>The output shape of the first graph is incompatible with the input shape of the second.</p>

<p>5031</p>

<p>warning_y_true_name</p>

<p>The name shown is not a driveable output of the model.</p>

<p>5032 – 5033</p>

<p>check_pool_shape</p>

<p>The kernel size or the stride does not have the right shape or right values.</p>

<p>5034</p>

<p>check_filter_units</p>

<p>The value assigned to the “n_filters” parameter must be strictly positive.</p>

<p>5035</p>

<p>check_embedding_input_output_dim</p>

<p>The</p>

<p>Embedding</p>

<p>layer must have strictly positive the “input_dim” and “output_dim” parameters value.</p>

<p>5036</p>

<p>check_rnn_gpu_integration</p>

<p>The “activation” parameter(s) of the cells sent to the RNN layer is not compatible with the CuDNN version.</p>

<p>5037</p>

<p>check_fit_metric_best</p>

<p>The metric selected in the “Comparison Metric” parameter of the “Fit” function is not in the ‘metrics_array’.</p>

<p>5038</p>

<p>check_multi_input_batch</p>

<p>The batch size is not the same for every inputs of operand layer (</p>

<p>Add</p>

<p>or</p>

<p>Average</p>

<p>or</p>

<p>Multiply</p>

<p>or</p>

<p>Substract</p>

<p>).</p>

<p>5040 – 5042</p>

<p>check_gpu_ready</p>

<p>Your gpu is not ready. You must have a CUDA compatible graphics card or install CUDA. You can use our</p>

<p>installer</p>

<p>to start the installation.</p>

<p>5043</p>

<p>warning_attention_scale</p>

<p>The AdditiveAttention layer has no weight because “use_scale” == False.</p>

<p>5044</p>

<p>check_index</p>

<p>The index specified doesn’t exist in the graph.</p>

<p>5050</p>

<p>Licence not installed</p>

<p>The licence is not installed so toolkit could not run.</p>

<p>5051</p>

<p>Licence expired</p>

<p>Licence expired so toolkit could not run.</p>

<p>5052</p>

<p>Runtime Error</p>

<p>Their is a Runtime error so could not run</p>

<p>5053</p>

<p>Reactivation needed</p>

<p>Licence Reactivation needed (Use SOTA to reactivate the licence on the computer)</p>
