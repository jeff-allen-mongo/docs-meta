Before the new screenshot is transfered to the ``source/images``
folder, you are given the opportunity to verify the image looks
as expected by checking the ``screenshots-temp`` folder in the
repository's root directory.

.. example::

   The following example goes through an array of screenshots called
   ``screenshot_names``, compares the screenshots, and for each
   screenshot the tool deems to be different than the original image,
   prompts the user to overwrite the original image.

   .. code-block:: javascript

      for (const image of screenshot_names) {
         await util.compareImages(image);
      }

After grabbing an image, if an image with the same name already
exists in the ``source/image`` repository, the script presents
a *mismatch percentage* (brought to you by
`ResembleJS <https://www.npmjs.com/package/node-resemble-js>`_). The
script places the new screenshot as well as an image analysis file
into the ``screenshots-temp`` folder. The image analysis file
pinpoints exactly where the new screenshot differs from the original
image so you can check before answering the prompt.

.. note::

   Manually comparing images is largely for debugging purposes. If
   the script is running as expected, it should be safe to replace
   the image automatically without comparing first.
