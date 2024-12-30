GNU Privacy Guard
-----------------

- Generating a new keypair

      gpg --full-gen-key

- Exchanging keys

      gpg --list-keys

- Exporting a public key

      gpg --output alice.gpg --export alice@cyb.org
      gpg --output alice.pub --armor --export alice@cyb.org

- Importing a public key

      gpg --import tianlin_pub.gpg

- Encrypting and decrypting documents

      gpg --output doc.gpg --encrypt --recipient tianlin.w@gmail.com doc
      gpg --output doc --decrypt doc.gpg

- Making and verifying signatures

  - Direct signature

        gpg --output doc.sig --sign doc
        gpg --verify doc.sig

  - Clearsigned documents

        gpg --clearsign doc
        gpg --verify  doc.asc

  - Detached signatures

        gpg --output doc.sig --detach-sig doc
        gpg --verify doc.sig doc

- Extract the original document from the signed document

      gpg --output doc --decrypt doc.sig

- Validating other keys on your public keyring

      gpg --edit-key tianlin_wang@yahoo.com
      fpr
      sign
      quit

