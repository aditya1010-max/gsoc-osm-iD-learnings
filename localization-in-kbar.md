Localization(l10n) means adapting software so that it can woork correctly for users in different languages and regions.

The Core Idea;

Instead of hardcoding:
title: 'Add Point'

You write:
title: () => t('modes.add_point.title')

And somewhere else:
{
"modes": {
"add_point": {
"title": "Add Point"
}
}
}

Then for French:

{
"modes": {
"add_point": {
"title": "Ajouter un point"
}
}
}

The software picks the correct one based on user language.

That’s localization.
