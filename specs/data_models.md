# Спецификация функции: Модели Данных и Моки (Data Models & Mocks)

Поскольку разработка Frontend'а начнется до готовности реального Backend'а (Базы данных), этот документ задает стандарты (TypeScript Interfaces) для основных структур данных. 

ИИ обязан использовать эти структуры при создании компонентов и генерации временных данных (Mock Data).

## 1. Товар (Product)
Модель для физического товара (БАДа/Витамина).

```typescript
interface IProduct {
  id: string; // Уникальный идентификатор (UUID)
  title: string; // "Магний Хелат 400мг"
  slug: string; // "magnesium-chelate-400" (для URL)
  price: number; // Цена в базовой валюте
  old_price?: number; // Старая цена (для показа скидки)
  stock_quantity: number; // Остаток на складе (для контроля)
  category: "vitamins" | "minerals" | "complexes";
  tags: string[]; // Микро-теги: ["Для сна", "Анти-стресс"]
  images: string[]; // Массив URL картинок
  description: string; // Подробное описание (HTML или Markdown)
  ingredients: IIngredient[]; // Состав
  rating: number; // От 1.0 до 5.0
  reviews_count: number;
}

interface IIngredient {
  name: string; // "Бисглицинат магния"
  amount: string; // "400 мг"
  daily_value_percent?: number; // "100%"
}
```

## 2. Курс (Course)
Модель для цифрового оздоровительного курса.

```typescript
interface ICourse {
  id: string;
  title: string; // "Здоровый ЖКТ за 30 дней"
  slug: string; // "healthy-gastro-30"
  price: number;
  duration_days: number; // Длительность доступа (например, 180 дней)
  thumbnail: string; // URL обложки курса
  short_description: string;
  modules: ICourseModule[]; // Уроки
  is_active: boolean;
}

interface ICourseModule {
  id: string;
  title: string; // "Модуль 1: Очищение"
  lessons_count: number;
}
```

## 3. Пользователь (User Profile)
Структура данных авторизованного пользователя.

```typescript
interface IUserProfile {
  id: string;
  email: string;
  full_name?: string;
  phone?: string;
  purchased_courses: {
    course_id: string;
    purchased_at: string; // ISO Date
    expires_at: string; // ISO Date (для расчета таймера)
  }[];
  orders: IOrderSummary[];
}
```

## 4. Корзина (Cart Item)
Элемент корзины, сохраняемый в LocalStorage.

```typescript
interface ICartItem {
  product_id: string; // Ссылка на товар
  quantity: number; // Не может превышать stock_quantity
  selected_options?: Record<string, string>; // Например, { volume: "120 капсул" }
}
```
