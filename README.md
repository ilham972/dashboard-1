1. > npx create-next-app@latest
   > npx shadcn-ui@latest init

2. page.tsx(delete everything), layout.tsx(meta), global.tsx ->
   (html,
   body,
   :root {
   height: 100%;
   })

   - create 3 root folders inside (root),(dashboard),(auth) with own layout.tsx for each
   - move page.tsx inside (root)
     > shadcn-ui@latest add - then select button, form , input , dialog(all shadcn components are constant export)

   ## clerk authentication

   - create .env and git ignore

3. create distribution for modal
   layout.tsx/ - import <ModalProvider>
   providers/modal-provider.tsx/ - create modal provider

4. create model in 3 steps

   1. components/modal.tsx
   2. hooks/use-store-modal.tsx
   3. modals/store-modal.tsx
   4. inlcude form

5. > npm i-D prisma
   > npm install @prisma/client
   > npx prisma init

   - now prisma/shema.prisma file create and connection string added to env file
     inside lib folder(create by shadcn) create prismadb.ts and write

6. connect the planet scale
   get the connection string and add to env file
   get the schma.prisma add it to prisma/schema.prisma
   now connected

7. create model store inside schema.prisma

   > npx prisma generate

   - now we can use prismadb as client by import any where because node modules updated,
   - we can also use that store what we created inside shema.prisma

8. now connect our prisma shcema into planet scale database

   > npx prisma db push

   - ok now table create in planet scale db

9. create api route for store
   app/api/stores/route.ts

   - so this will handle for creating store for user in mysql db

10. stor-modal/

- add loading state in store-modal
  > npm i axios and edit the store-model in onsubmit-function-block for http or store modal route
  > npm i react-hot-toast
- create provider/toast-provider.tsx and write and then import toast-provider inside layout
- now import toast from react-hot-toast into store modal and change the console.log(error) with toast

11. create folder app/(dashboard)/[storeid]/layout.tsx

    - write the code inside layout.tsx - for authentication and check existing store

12. create folder /[storeid]/(routes)/page.tsx and write

13. create (root)/layout.tsx and write

- create (root)/(routes) and then move the page.tsx into this folder and return null in page.tsx

14. recreate the database
    > npx prisma migrate reset
    > npx prisma generate
    > npx prisma db push
