.. _adapt_acoustic_model:

Adapt acoustic model to new data ``(mfa adapt)``
================================================

A recent 2.0 functionality for MFA is to adapt pretrained :term:`acoustic models` to a new dataset.  MFA will first align the dataset using the pretrained model, and then update the acoustic model's GMM means with those generated by the data.  See :kaldi_steps:`train_map` for the Kaldi script this functionality corresponds to.  As part of the adaptation process, MFA can generate final alignments and export these files if an output directory is specified in the command.


.. note::

   You can use manual or verified reference alignments in adaptation to bypass the initial round of alignment for some or
   all files and these alignments will be used for adjusting the acoustic model parameters.  See :ref:`reference_alignment_format`
   for more information on how to include these alignments.


.. seealso::

   See :xref:`mfa_adaptation_scripts` for reference files and CLI commands that are have been used for evaluating performance of adaptation.

Command reference
-----------------

.. click:: montreal_forced_aligner.command_line.adapt:adapt_model_cli
   :prog: mfa adapt
   :nested: full

Configuration reference
-----------------------

- :ref:`configuration_global`
- :ref:`configuration_adapting`

API reference
-------------

- :class:`~montreal_forced_aligner.alignment.AdaptingAligner`
