# symfony

## Installation

Créez le fichier docker-compose.yml

```bash
$ docker-compose up -d --build
$ docker-compose exec web symfony new . --version="7.2.x" --webapp --no-interaction
```
## Création du controller

```bash
$ touch src/Controller/LuckyController.php
```

*src/Controller/LuckyController.php*

```php
<?php
// src/Controller/LuckyController.php
namespace App\Controller;

use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Attribute\Route;
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;

class LuckyController extends AbstractController
{
    #[Route('/lucky/number')]
    public function number(): Response
    {
        $number = random_int(0, 100);

        /*return new Response(
            '<html><body>Lucky number: '.$number.'</body></html>'
        );*/
        return $this->render('lucky/number.html.twig', [
            'toto' => $number,
        ]);
    }
}
```

## Créer la base de donnée

```

```