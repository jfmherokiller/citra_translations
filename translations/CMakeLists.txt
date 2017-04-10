set_directory_properties(PROPERTIES CLEAN_NO_CUSTOM 1)


#language file names follow the format of translations[_language[ _country]]
#language is the ISO-639 2 letter language code
#country is the ISO-3166 2 letter country code
set(LANGS
        translations_en_us.ts
        translations_de_de.ts
        translations_fr_fr.ts
        translations_ja_jp.ts
        )
qt5_create_translation(TRANSLATION_MESSAGES ${CITRA_SRC} ${CITRA_HDR} ${CITRA_UI} ${LANGS})
qt5_add_translation(TRANSLATION_QM ${LANGS})
add_custom_target(translations_update ALL DEPENDS citra ${TRANSLATION_MESSAGES})
add_custom_target(translations DEPENDS translations_update ${TRANSLATION_QM})
