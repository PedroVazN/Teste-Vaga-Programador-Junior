# Instruções

## Instalação

1. Instale o Django:
```bash
pip install Django
```

2. Crie as migrações:
```bash
python manage.py makemigrations
```

3. Aplique as migrações:
```bash
python manage.py migrate
```

4. Crie o usuário administrador:
```bash
python manage.py createsuperuser
```

5. Execute o servidor:
```bash
python manage.py runserver
```

## Criar Questões e Respostas

Você pode criar Questões e Respostas de duas formas:

### Opção 1: Usando o Admin
Acesse `http://127.0.0.1:8000/admin/` e crie manualmente.

### Opção 2: Usando o Shell do Django
```bash
python manage.py shell
```

No shell, execute:
```python
from django.utils import timezone
from polls.models import Question, Choice
import datetime

q1 = Question.objects.create(
    question_text="Qual é a sua linguagem de programação favorita?",
    pub_date=timezone.now() - datetime.timedelta(days=5)
)
Choice.objects.create(question=q1, choice_text="Python", votes=10)
Choice.objects.create(question=q1, choice_text="JavaScript", votes=8)
```

## Testar

1. Acesse `http://127.0.0.1:8000/polls/`
2. Vote em uma questão
3. Veja os resultados em `/polls/<id>/results/`
