# Translate

This page is all about how to create translations for YoutubeDL-Material. If you are simply trying to set your language within the app, you can find that option in the settings menu.

## Introduction (for beginners)

Translating YoutubeDL-Material into a new language is a multi-step process. It begins with the `messages.en.xlf` file, which contains virtually all strings, (referred to as *source string*) within the UI in English. This is usually called a *source file*, and is of type [XLIFF](https://en.wikipedia.org/wiki/XLIFF).

The *target file* contains both the source string and the *target string*, which is the translated string in the target language. Here is an excerpt from `messages.es.xlf` file ([view here](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/src/assets/i18n/messages.es.xlf)), which is the English->Spanish translation of YoutubeDL-Material:

	<trans-unit id="cff1428d10d59d14e45edec3c735a27b5482db59">
		<source>Name</source>
		<target>Nombre</target>
	</trans-unit>

The source string and target string are clearly visible within the `trans-unit` object.

The front end uses the `id` in `trans-unit` to connect the original string in the app with the translated string.

Translating each string manually would take a while, so you can use [Computer-Assisted Translation](https://en.wikipedia.org/wiki/Comparison_of_computer-assisted_translation_tools#References) to help you out with that like [OmegaT](https://omegat.org/) or the web-based (with a solid free version) [SmartCat](https://us.smartcat.ai/).

Ultimately, the resulting translation file must be converted to JSON for consumption by the UI (`messages.es.xlf` would become `messages.es.json`). The reason for this is that JSON files are far smaller than XLIFFs (about 1/5 the size), and are easier to read for JavaScript-based applications.

Here is that example string shown above, this time in the `messages.es.json` file ([view here](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/src/assets/i18n/messages.es.json)):

	"cff1428d10d59d14e45edec3c735a27b5482db59": "Nombre",

See? A much smaller footprint! But, you may ask, isn't it incredibly tedious that I now have to convert my target XLIFF to a JSON? I felt the same way, so I created a program that takes care of that called [xliff-to-json](https://github.com/Tzahi12345/xliff-to-json). It simply takes 1 command to generate your desired JSON containing your translated strings.

## Translation Process

Make sure you read through the Introduction above to get yourself familiarized with the process. This section assumes you have gone through that, and are now looking to create a new translation for YoutubeDL-Material. If that's the case, awesome! Read through the following steps.

1. Download the latest [source XLIFF file](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/src/assets/i18n/messages.en.xlf) in the `src/assets/i18n` folder in the repository.
2. Use your favorite CAT (computer-assisted translation) tool to translate the `messages.en.xlf` file into a target `messages.{CODE}.xlf` file, where `{CODE}` is the target language's [ISO 639-1 Code](https://www.loc.gov/standards/iso639-2/php/code_list.php). For example, English is `en` and Spanish is `es`.
3. Use xliff-to-json to convert the `messages.{CODE}.xlf` to `messages.{CODE}.json`, which is the correct format for consumption by the UI. Verify that the resulting JSON has the correct format.
4. If everything is looking A-OK, the next step is to submit a PR that contains your new translation. This PR should take care of 3 things:
* Add the new target XLIFF file to the `src/assets/i18n` folder.
* Add the new target JSON file to the `src/assets/i18n` folder.
* Add the new language code to the `supported_locales` in the `settings.component.ts` file [here](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/src/app/settings/settings.component.ts)

The last requirement for the PR (adding the new language code) is the least important one, so if you simply add the target `xliff` and `json` files, I can handle the rest.

And that's pretty much it! Once your PR is merged, then the translations should be available in the next update. If you're having trouble with any of these steps, create an issue and I'll be happy to help.