
.. _changelog_2.2:

*************
2.2 Changelog
*************

2.2.4
=====

- Fixes an issue where some directories in Common Voice Japanese were causing FileNotFound errors for sound files
- Changes PostgreSQL database connections to use socket directories rather than ports
- Added the ability to manage MFA database servers (:ref:`server`), along with the configuration flag to disable automatic starting/stopping of databases
- Disabled starting servers for subcommands like ``configure``, ``version``, ``history`` or ``--help`` invocations
- Added support for handling spaces when running :ref:`mfa g2p <g2p_dictionary_generating>` (though very simple as it just concatenates the outputs, and if ``--num_pronunciations`` is set to something other than 1, it is ignored)
- Added the ability to pipe words via stdin/stdout when running :ref:`mfa g2p <g2p_dictionary_generating>`
- Added the ability to generate pronunciations per utterance when running :ref:`mfa g2p <g2p_dictionary_generating>`
- Added a first pass at providing estimations of alignment quality through the ``alignment_analysis.csv`` file exported with alignments, see :ref:`alignment_analysis` for more details.

2.2.3
=====

- Update terminal printing to use :mod:`rich` rather than custom logic
- Prevented the tokenizer utility from processing of text files that don't have a corresponding sound file

2.2.2
=====

- Fixed a rounding issue in parsing sox output for sound file duration
- Added ``--dictionary_path`` option to :ref:`g2p_dictionary_generating` to allow for generating pronunciations for just those words that are missing in a dictionary
- Added ``add_words`` subcommand to :ref:`pretrained_models` to allow for easy adding of words and pronunciations from :ref:`g2p_dictionary_generating` to pronunciation dictionaries

2.2.1
=====

- Fixed a couple of bugs in training Phonetisaurus models
- Added training of Phonetisaurus models for tokenizer

2.2.0
=====

- Add support for training tokenizers and tokenization
- Migrate most os.path functionality to pathlib
