(  https://eslint.org/docs/latest/use/getting-started  )
(  https://soykje.gitlab.io/en/blog/nextjs-typescript-eslint/  )
(  https://nextjs.org/docs/basic-features/eslint  )

1)   npm init @eslint/config

2)   npm install -D  eslint-plugin-react-hooks eslint-plugin-jsx-a11y

3)  Add code blow to".eslintrc.json" file:

        {
            "settings": {
                "react": {
                    "version": "detect"
                }
            },
            "env": {
                "browser": true,
                "es2021": true,
                "node": true
            },
            "extends": [
                "eslint:recommended",
                "plugin:react/recommended",
                "plugin:react-hooks/recommended",
                "plugin:jsx-a11y/recommended",
                "plugin:prettier/recommended"
            ],
            "parserOptions": {
                "ecmaFeatures": {
                    "jsx": true
                },
                "ecmaVersion": 12,
                "sourceType": "module"
            },
            "plugins": ["react", "jsx-a11y"],
            "rules": {
                "react/react-in-jsx-scope": "off",
                "jsx-a11y/anchor-is-valid": "off"
            },
            "overrides": [
                {
                    "files": ["**/*.ts", "**/*.tsx"],
                    "parser": "@typescript-eslint/parser",
                    "plugins": ["@typescript-eslint"],
                    "extends": ["plugin:@typescript-eslint/recommended"],
                    "rules": {
                        "prettier/prettier": "off",
                        "semi": [2, "always"],
                        "quotes": ["error", "single"],
                        "max-len": ["error", { "code": 100 }],
                        "indent": ["error", 4],
                        "no-multiple-empty-lines": ["error", { "max": 1 }]
                    }
                }
            ]
        }

4)  npm install -D prettier eslint-plugin-prettier eslint-config-prettier

5)  Create ".prettierrc.json" file and add:

        {
            "trailingComma": "es5",
            "semi": true,
            "singleQuote": true,
            "printWidth": 100,
            "tabWidth": 4,
            "importOrder": ["@(.*)$", "^[./]", "@components/(.*)$"],
            "importOrderSeparation": true,
            "importOrderSortSpecifiers": true,
            "importOrderCaseInsensitive": true
        }
