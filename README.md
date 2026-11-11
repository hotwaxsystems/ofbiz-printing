# OFBiz Printing

A plugin for Apache OFBiz that prints labels and documents on printers in the warehouse or store.
PrintNode is the first print provider. PrintNode is a cloud service that sends print jobs to printers on a local network.

## How it works

- Printers are synced from the provider, with their status.
- Printer rules say which printer each kind of document goes to: for a facility, a station or a user. The most specific rule wins.
- Every print job is recorded: the document, the printer, the user and the time. Reprints are marked.
- A job is sent only after the database change that asked for it is saved.
- Documents print as PDF. Labels print as raw ZPL on thermal label printers.
- ZPL label templates are filled from record fields, with a preview.
- Every provider follows one shared set of services: list printers, send a job, read a job's state.
- It does not change OFBiz core code.

## Install

Clone this repository into the `plugins` folder of an OFBiz trunk checkout:

```
cd ofbiz-framework/plugins
git clone https://github.com/hotwaxsystems/ofbiz-printing.git printing
```

## Contributing

Every change goes through a pull request.

## License

Apache License 2.0. See `LICENSE` and `NOTICE`.
