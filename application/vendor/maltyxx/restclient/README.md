# restclient
REST Full Client for Codeigniter 3

## Requirements

- PHP 5.3.x (Composer requirement)
- CodeIgniter 3.x.x

## Installation
### Step 1 Installation by Composer
#### Run composer
```shell
composer require maltyxx/restclient
```

### Step 2 Examples
Cotroller file is located in `/application/controllers/Client.php`.
```php
<?php
defined('BASEPATH') OR exit('No direct script access allowed');

class Client extends CI_Controller
{
    public function index()
    {
        $this->load
            ->add_package_path(FCPATH.'vendor/restclient')
            ->library('restclient')
            ->remove_package_path(FCPATH.'vendor/restclient');

        $this->load->helper('url');

        $json = $this->restclient->post(site_url('server'), [
            'lastname' => 'test'
        ]);

        $this->restclient->debug();
    }
}
```
