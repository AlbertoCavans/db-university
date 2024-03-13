## dipartimenti

| FILED                | TYPE_DATA | ATTRIBBUTES |
| -------------------- | --------- | ----------- |
| id                   |           |             |
| settore_dipartimento |           |             |
| nome_dipartimento    |           |             |

## corsi_di_laurea

| FILED              | TYPE_DATA | ATTRIBBUTES |
| ------------------ | --------- | ----------- |
| id                 |           |             |
| id_dipartimento    |           |             |
| anni_corso         |           |             |
| responsabile_corso |           |             |

## corsi

| FILED              | TYPE_DATA | ATTRIBBUTES |
| ------------------ | --------- | ----------- |
| id                 |           |             |
| id_corsi_di_laurea |           |             |
| studenti_iscritti  |           |             |
| ore_necessarie     |           |             |

## insegnanti

| FILED    | TYPE_DATA | ATTRIBBUTES |
| -------- | --------- | ----------- |
| id       |           |             |
| id_corsi |           |             |
| nome     |           |             |
| email    |           |             |

## studenti

| FILED            | TYPE_DATA | ATTRIBBUTES |
| ---------------- | --------- | ----------- |
| id               |           |             |
| nome             |           |             |
| numero_matricola |           |             |
| data_nascita     |           |             |

## appelli_esame

| FILED        | TYPE_DATA | ATTRIBBUTES |
| ------------ | --------- | ----------- |
| id           |           |             |
| id_studenti  |           |             |
| data_appello |           |             |
