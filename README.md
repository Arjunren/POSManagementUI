# POS Management UI

## Overview

A responsive café point-of-sale interface for menu discovery, category/search filtering, cart quantities, tax totals, and simulated checkout.

## Features

Asynchronous catalog loading, category and text filters, stock-aware quantities, live totals and tax, clear order, checkout receipt state, keyboard-friendly controls, empty states, and responsive counter/mobile layouts.

## Technology Stack

React 19, TypeScript 7, Vite 8, Lucide icons, Testing Library, Vitest 5, Nginx, and Docker.

## Requirements / Installation

Install Node.js 24+ and npm 11+, then run `npm install`.

## Environment Variables

`VITE_API_BASE_URL` is documented in `.env.example`. Browser-exposed variables must never contain credentials.

## Database Setup

This independently runnable frontend uses `src/services/catalog.ts` as a mock API boundary and requires no database.

## Running the Application

Run `npm run dev`; create a production bundle with `npm run build`.

## Running Tests

Run `npm run check`. Tests cover cart pricing, category filtering, and search.

## Default Development Accounts

The interface shows development cashier persona Nina R.; production authentication belongs on the backend.

## API Endpoints

A production backend should provide catalog, stock, order, payment, and receipt endpoints beneath `VITE_API_BASE_URL`.

## Folder Structure

`components` contains catalog/cart views, `services` is the replaceable data boundary, `types` contains contracts, and `tests` contains user-interaction coverage.

## Security Notes

React escapes displayed values and no secrets or payment details are persisted. Client totals and stock checks are display conveniences only: a backend must authenticate cashiers, authorize discounts/refunds, calculate authoritative totals/tax, validate stock, enforce idempotent payment requests, and avoid storing card data directly.

## Known Limitations

Barcode hardware, receipt printing, offline synchronization, discounts, split payments, and a real payment processor are outside scope.

## License

MIT
