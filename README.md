# Memory Vault: Private Memories

A web application to securely store and view private memories. Users can sign in to access private photos stored in Azure Blob Storage. This project demonstrates secure file storage integration with Azure and a user-friendly interface for managing private content.

---

## Features

- **User Authentication**:
  - Sign-in functionality to restrict access to private content.
  - Session-based authentication using `sessionStorage`.

- **Secure File Storage**:
  - Integration with **Azure Blob Storage** to store and retrieve private photos.
  - Secure access using Azure **Shared Access Signature (SAS) tokens**.

- **Responsive Design**:
  - Clean and responsive UI for an optimal user experience on all devices.

---

## Project Structure

```
memory-vault-main/
├── public/
│   ├── index.html          # Home page
│   ├── about.html          # About Us page
│   ├── private.html        # Private page (authenticated users only)
│   ├── signin.html         # Sign-in page
│   ├── styles.css          # Shared styles
│   └── uploads/            # Folder for uploaded files (if used locally)
├── .env                    # Environment variables (for sensitive data)
├── .gitignore              # Files and folders to ignore in Git
├── package.json            # Node.js dependencies
├── server.js               # Node.js server file
└── README.md               # Project documentation (this file)
```

---

## Getting Started

Follow these instructions to set up and run the project locally or on a server.

### Prerequisites

- [Node.js](https://nodejs.org/) installed on your machine.
- An **Azure Storage Account** with a container for storing private memories.
- A valid **SAS Token** with `Read` and `List` permissions for the container.

---

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/memory-vault.git
   cd memory-vault
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Set Up Environment Variables**:
   - Create a `.env` file in the root directory and add your Azure Blob Storage details:
     ```
     STORAGE_URL=https://<your-storage-account>.blob.core.windows.net/<container-name>
     SAS_TOKEN=?sv=2024-11-29&ss=b&srt=sco&sp=rl&se=2024-12-01T23:59:00Z&st=2024-11-29T00:00:00Z&spr=https&sig=abcdefghijklmnopqrstuvwxyz1234567890
     ```

4. **Start the Server**:
   ```bash
   node server.js
   ```

5. **Access the Application**:
   - Visit `http://localhost:5500` in your browser.

---

## Usage

1. **Sign In**:
   - Navigate to the **Sign In** page and enter valid credentials.

2. **Access Private Content**:
   - After signing in, you will be redirected to the **Private Memories** page where you can view photos stored in Azure Blob Storage.

3. **Sign Out**:
   - Click the **Sign Out** button to end the session.

---

## Azure Blob Storage Integration

- **Container URL**:
  ```
 [ https://<your-storage-account>.blob.core.windows.net/<container-name>](https://cloudtask5.blob.core.windows.net/private-memories)
  ```

- **SAS Token**:
  - A **Shared Access Signature (SAS)** token is used for secure access to the Blob Storage container. The token should have at least `Read` and `List` permissions.

---

## Technologies Used

- **Frontend**:
  - HTML5, CSS3, JavaScript
- **Backend**:
  - Node.js with Express.js
- **Cloud Storage**:
  - Azure Blob Storage

---

## How It Works

1. **User Authentication**:
   - Users must sign in to access private content. Authentication is managed using `sessionStorage`.

2. **Private Photos**:
   - The app fetches private photos from Azure Blob Storage using a secure `fetch` request with the container URL and SAS token.

3. **Error Handling**:
   - If the SAS token is invalid or the container is empty, the app displays appropriate error messages.

---

## Future Enhancements

- Add a **registration page** for new users.
- Implement **file upload** functionality to allow users to upload their own photos to Azure Blob Storage.
- Add **role-based access control** for enhanced security.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contributors

- [Izhan Sohail](https://github.com/your-username)

Feel free to contribute to this project by creating a pull request or submitting issues.
