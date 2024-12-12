# NextAuth Session Undefined After Navigation in Next.js 15

This repository demonstrates a bug where the NextAuth session becomes undefined after navigating to a page that requires authentication. The session is correctly defined on the initial page load but loses its value after navigation.

## Bug Description

The `unstable_getServerSession` function is used to retrieve the user's session, which is correctly retrieved on the initial load of the `/about` page. However, after navigating from the `/` page to the `/about` page, the session object is undefined, resulting in a rendering error.

## Bug Reproduction

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Navigate to `/about`.
5. Observe that the session is correctly defined.
6. Navigate to `/` and then back to `/about`.
7. Observe that the session is now undefined.

## Solution

The solution involves refactoring to utilize the `useSession` hook from `next-auth/react` for client-side session management.  This ensures that the session data is persisted across client-side navigation.

## Technologies Used

* Next.js 15
* NextAuth.js

## License

MIT