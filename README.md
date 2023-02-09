### Detailed steps to reproduce the issue on the reproducing repository:
> Meilisearch must be installed locally in order to fully test it.
1. Copy `.env.example` to `.env`
2. Change `MEILISEARCH_HOST` and `MEILISEARCH_KEY` if not using default settings
3. Create database `nova_search_issue`
4. Run `composer install`
5. Run `php artisan key:generate`
6. Run `php artisan migrate:fresh --seed`
7. Index users by running `php artisan scout:import "App\Models\User"`
8. Add it to valet by running `valet link`
9. Login to nova with `john@doe.com` and `password` as password.
10. Navigate to `/nova/resources/roles`
11. Select a random role
12. Try to search for a user and notice that unrelated users appear and `notes` pivot field is empty.


![Screenshot 2023-02-09 at 1 54 37 PM](https://user-images.githubusercontent.com/6439071/217807608-d0b8b2e5-2f8e-40b1-b27a-1385608258ed.png)
