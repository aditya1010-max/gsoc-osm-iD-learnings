Localization(l10n) means adapting software so that it can woork correctly for users in different languages and regions.

The Core Idea;

Instead of hardcoding:
title: 'Add Point'

You write:
title: () => t('modes.add_point.title')
