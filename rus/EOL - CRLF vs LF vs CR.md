## Разница между CRLF, LF и CR? (EOL)

EOL - End Of Line - конец строки:
- LF - Linux, Mac > версии 9
- CR - Mac <= версии 9
- CRLF - Windows

Это о переводе строки. CR (Carriage Return) - возврат каретки, LF (Line Feed) - подача строки. Просто контрольные символы. При разработке проекта на разных ОС могут возникать проблемы из-за этого, поэтому важно контролировать их.

### Ссылки

- [StackOverflow](https://stackoverflow.com/questions/1552749/difference-between-cr-lf-lf-and-cr-line-break-types)
- [Wikipedia ENG](https://en.wikipedia.org/wiki/Newline)
- [Wikipedia RUS](https://ru.wikipedia.org/wiki/Перевод_строки)
