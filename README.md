# task-1
name: CD

on:
  workflow_run:
    workflows: ["CI"]
    branches:
      - main
    types:
      - completed

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Setup Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '14'
    - name: Install Dependencies
      run: npm install
    - name: Build and Deploy
      run: |
        npm run build
        # Add your deployment steps here
done okkkkkkk
