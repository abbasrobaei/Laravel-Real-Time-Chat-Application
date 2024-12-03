# Laravel-Real-Time-Chat-Application
A real-time chat application built with Laravel 11, featuring user authentication, private messaging, and real-time notifications.

## Features

- User registration and authentication
- Private messaging between users
- Real-time message updates using Pusher
- Unread message notifications
- Message read receipts
- Responsive design with Tailwind CSS

## Requirements

- PHP 8.2 or higher
- Composer
- Node.js and NPM
- MySQL 5.7 or higher
- Pusher account for real-time features

## Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/laravel-chat.git
cd laravel-chat
```

2. Install PHP dependencies
```bash
composer install
```

3. Install and compile frontend dependencies
```bash
npm install
npm run build
```

4. Create and configure environment file
```bash
cp .env.example .env
```

5. Configure your `.env` file with:
   - Database credentials
   - Pusher credentials
   - Application URL
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=your_database_username
DB_PASSWORD=your_database_password

BROADCAST_DRIVER=pusher
PUSHER_APP_ID=your_pusher_app_id
PUSHER_APP_KEY=your_pusher_app_key
PUSHER_APP_SECRET=your_pusher_app_secret
PUSHER_HOST=
PUSHER_PORT=443
PUSHER_SCHEME=https
PUSHER_APP_CLUSTER=your_pusher_cluster
```

6. Generate application key
```bash
php artisan key:generate
```

7. Run database migrations
```bash
php artisan migrate
```

## Running the Application

1. Start the development server
```bash
php artisan serve
```

2. In a separate terminal, run Vite for frontend assets
```bash
npm run dev
```

3. Access the application at `http://localhost:8000`

## Usage

1. Register a new account or log in
2. Navigate to the Messages section
3. Select a user to start a chat
4. Send messages and receive real-time updates

## Features in Detail

### Authentication
- Built using Laravel Breeze
- User registration with email verification
- Secure login system

### Messaging System
- Private messaging between users
- Real-time message delivery
- Message read status tracking
- Unread message notifications
- Chronological message display

### Real-Time Features
- Pusher integration for real-time updates
- Message delivery notifications
- Read receipts
- Unread message indicators

### User Interface
- Clean and responsive design
- User-friendly chat interface
- Unread message indicators with red star
- Message timestamps
- Read receipts

## Directory Structure

```
├── app
│   ├── Http
│   │   ├── Controllers
│   │   │   └── MessageController.php
│   ├── Models
│   │   ├── Message.php
│   │   └── User.php
│   └── Events
│       └── NewMessage.php
├── database
│   └── migrations
│       └── create_messages_table.php
├── resources
│   └── views
│       └── messages
│           ├── index.blade.php
│           └── show.blade.php
└── routes
    └── web.php
```

## Security Considerations

- All routes are protected with authentication
- CSRF protection enabled
- Private channels for broadcasting
- SQL injection protection through Laravel's query builder
- XSS protection through Laravel's {{ }} syntax

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Troubleshooting

### Common Issues

1. **Real-time updates not working**
   - Verify Pusher credentials in `.env`
   - Ensure Laravel Echo is properly configured
   - Check browser console for errors

2. **Database connection issues**
   - Verify database credentials in `.env`
   - Ensure MySQL service is running
   - Check database permissions

3. **Compilation issues**
   - Clear NPM cache and node_modules
   - Reinstall dependencies
   - Run `npm run build` again

### Additional Notes

- Ensure proper server configuration for WebSocket connections
- Configure your web server to handle long-lived connections for real-time features
- Set up proper cache configuration for optimal performance

## Credits

- Built with [Laravel](https://laravel.com)
- Real-time features powered by [Pusher](https://pusher.com)
- UI components from [Tailwind CSS](https://tailwindcss.com)
