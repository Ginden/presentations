This code was 
[taken from latextemplates.com](https://www.latextemplates.com/template/invoice).
Styling is present in file not included here.

```latex
\documentclass{invoice} % Use the custom invoice class (invoice.cls)
\def \tab {\hspace*{3ex}} % Define \tab to create some horizontal white space
\begin{document}
\hfil{\Huge\bf Initech Inc.}\hfil % Company providing the invoice
\bigskip\break % Whitespace
\hrule % Horizontal line
123 Broadway \hfill (000) 111-1111 \\ % Your address and contact information
City, State 12345 \hfill john@smith.com
\\ \\
{\bf Invoice To:} \\
\tab James Smith \\ % Invoice recipient
\tab Generic Corporation \\ % Recipient's company
{\bf Date:} \\
\tab \today \\ % Invoice date
\begin{invoiceTable}
\feetype{Consulting Services} % Fee category description
\hourrow{October 3, 2012}{8}{12} 
\subtotal % Prints a subtotal, can be used multiple times
\feetype{Hosting Expenses} % Fee category description
\feerow{Web Hosting: October, 2012}{60}
\end{invoiceTable}
\end{document}
```