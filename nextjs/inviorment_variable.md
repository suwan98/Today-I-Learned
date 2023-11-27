# Nextjs에서의 환경변수

## 규칙

**Nextjs에서의 환경변수 키워드는?**

> 📝 **NEXT_PUBLIC**

### 예시

```tsx
NEXT_PUBLIC_API_KEY = asdfasdfojelwek12312412;
```

**실제 로직에서 사용하려면?**

- `process.env` 키워드로 사용

```tsx
const API_KEY = process.env.NEXT_PUBLIC_API_KEY;
```
