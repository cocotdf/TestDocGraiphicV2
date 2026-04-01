<h1>coordinate_transformation_mode</h1>

<table>
  <tbody>
    <tr>
      <td width="64" valign="top"><img alt="Enum.Png" src="assets/enum.png" width="42"/></td>
      <td valign="top"><strong>coordinate_transformation_mode : <em>enum,</em></strong> this attribute describes how to transform the coordinate in the resized tensor to the coordinate in the original tensor.</td>
    </tr>
  </tbody>
</table>

<p>The coordinate of each dimension is transformed individually. Let’s describe a case using axis x as an example. Denote <code>x_resized</code> as the coordinate of axis x in the resized tensor, <code>x_original</code> as the coordinate of axis x in the original tensor, <code>length_original</code> as the length of the original tensor in axis x, <code>length_resized</code> as the length of the resized tensor in axis x, <code>scale = length_resized / length_original</code>, <code>output_width</code> the target length on the axis x which can be a fractional number when it is calculated out of a scale factor, and <code>output_width_int</code> the effective output width as an integer.</p>

<p>if coordinate_transformation_mode is <code>"half_pixel"</code>,</p>

<p>x_original</p>

<p>=</p>

<p>(</p>

<p>x_resized</p>

<p>+</p>

<p>0.5</p>

<p>)</p>

<p>/</p>

<p>scale</p>

<p>-</p>

<p>0.5</p>

<p>if coordinate_transformation_mode is <code>"half_pixel_symmetric"</code>,</p>

<p>adjustment</p>

<p>=</p>

<p>output_width_int</p>

<p>/</p>

<p>output_width</p>

<p>center</p>

<p>=</p>

<p>input_width</p>

<p>/</p>

<p>2</p>

<p>offset</p>

<p>=</p>

<p>center</p>

<p>*</p>

<p>(</p>

<p>1</p>

<p>-</p>

<p>adjustment</p>

<p>)</p>

<p>x_ori</p>

<p>=</p>

<p>offset</p>

<p>+</p>

<p>(</p>

<p>x</p>

<p>+</p>

<p>0.5</p>

<p>)</p>

<p>/</p>

<p>scale</p>

<p>-</p>

<p>0.5</p>

<p>if coordinate_transformation_mode is <code>"pytorch_half_pixel"</code>,</p>

<p>x_original = length_resized &gt; 1 ? (x_resized + 0.5) / scale - 0.5 : 0</p>

<p>if coordinate_transformation_mode is <code>"align_corners"</code>,</p>

<p>x_original</p>

<p>=</p>

<p>x_resized</p>

<p>*</p>

<p>(</p>

<p>length_original</p>

<p>-</p>

<p>1</p>

<p>)</p>

<p>/</p>

<p>(</p>

<p>length_resized</p>

<p>-</p>

<p>1</p>

<p>)</p>

<p>if coordinate_transformation_mode is <code>"asymmetric"</code>,</p>

<p>x_original</p>

<p>=</p>

<p>x_resized</p>

<p>/</p>

<p>scale</p>

<p>if coordinate_transformation_mode is <code>"tf_crop_and_resize"</code>,</p>

<p>x_original = length_resized &gt; 1 ? start_x * (length_original - 1) + x_resized * (end_x - start_x) * (length_original - 1) / (length_resized - 1) : 0.5 * (start_x + end_x) * (length_original - 1)</p>
