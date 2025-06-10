
# Annotate Greek Suntax  - User's Guide

This web app helps you annotate tokens in a Greek text, focusing on sentence connections, verbal units within a sentence, and syntactic relations among tokens.

**1. Load Corpus and Choose Sentence:**
*   **Load Data:**
    *   The app starts with a default URL for a Herodotus text. You can replace this with a URL to any CEX-formatted citable corpus.
    *   Click the "Load CEX Data" button.
    *   Wait for the "Corpus loaded. Select a sentence." status message.
*   **Select Sentence:**
    *   Choose a sentence from the "Select Sentence:" dropdown menu. This will populate the "Annotate Sentence" display.

**2. Annotate Sentence:**
This is the main area where you'll interact with the text.

*   **Asyndeton / Connecting Word (First Annotation Step):**
    *   This section appears after you select a sentence. **You must complete this step before other annotation features become fully active.**
    *   If the sentence illustrates asyndeton, check the "This sentence illustrates asyndeton" box.
    *   Otherwise, click directly on the single lexical token in the "Annotate Sentence" display below that acts as the connecting word. The token will be highlighted yellow.
*   **Select Verbal Unit to assign tokens to:**
    *   This dropdown menu appears directly above the sentence tokens once "Asyndeton / Connecting Word" is completed.
    *   **To use this, you must first define at least one verbal unit in the "Define Verbal Units" section (see below).**
    *   Once verbal units are defined and one is selected here, click on lexical tokens in the "Annotate Sentence" display (token display with superscript numbers) to assign them to the selected verbal unit.
    *   Clicking a token again will unassign it from the *currently selected* verbal unit.
    *   Assigned tokens will be highlighted with their verbal unit's color.
*   **"Annotate Sentence" Display:**
    *   This area shows the tokens of the selected sentence. Lexical tokens are clickable (for Annotation 1 and for assigning to verbal units) and show their sequence number as a superscript.
    *   Tokens in this display will also receive text decorations (underline, overline, border) based on the relations you define in the "Define Token Relations" table (see "Define Token Relations" below).

**3. Verbal Unit Structure:**
*   This section (collapsible via the `[–]` / `[+]` button) displays the text of tokens that you have assigned to verbal units.
*   Tokens belonging to the same verbal unit appear on the same line.
*   A new line starts for tokens belonging to a different verbal unit.
*   Lines are indented based on the "Depth" you assigned to the verbal unit (Deeper VUs are indented further).
*   Tokens are colored according to their assigned verbal unit, and also receive text decorations based on "Define Token Relations."

**4. Define Verbal Units:**
*   This section (found further down, below the visualizations) is where you define the verbal units present in the sentence. It becomes active after completing "Asyndeton / Connecting Word."
*   For each verbal unit:
    *   Choose a "Syntactic Type" from the dropdown.
    *   Choose a "Semantic Type" from the dropdown.
    *   Enter an integer for "Depth" (e.g., 0 or 1 for main clauses, 2 for the next level of subordination, etc.).
    *   Click "Add and Confirm Verbal Unit".
*   Each verbal unit will be added to a table and assigned a unique pastel color. You can delete units from this table.
*   **Defining verbal units here makes them available in the "Select Verbal Unit to assign tokens to:" dropdown above the sentence display.**

**5. Syntax Graph Visualization & Define Token Relations:**
These sections become active only after you have:
    1.  Completed "Asyndeton / Connecting Word."
    2.  Defined at least one verbal unit.
    3.  Assigned **more than one token** to at least one verbal unit.

*   **Syntax Graph Visualization:**
    *   This section (collapsible via `[–]` / `[+]`) displays a directed graph representing the relationships defined in the "Define Token Relations" table below it.
    *   Use the "Graph Orientation:" dropdown to choose between "Top to bottom" (Mermaid `BT`) or "Left to right" (Mermaid `RL`).
*   **Define Token Relations:**
    *   This table is initially populated with all lexical tokens from the selected sentence.
    *   For each token (identified by its "Reference" number, which is its sequence in the sentence):
        *   "Token": The text of the token (not editable).
        *   "Node 1 (ID)": Enter the "Reference" number of another token it relates to.
        *   "Node 1 Relation": Select the type of relation from the dropdown.
        *   "Node 2 (ID)" & "Node 2 Relation": Optionally define a second relationship for the token.
    *   **Implied Tokens:** Click "Add Implied Token Row" to create a row for a token that is grammatically implied but not explicit in the text. You can then link other tokens to this implied token's "Reference" number.
    *   Changes in this table will automatically update the "Syntax Graph Visualization" and the text decorations on tokens in the "Annotate Sentence" display and "Verbal Unit Structure" display.

**6. Download Annotations:**
*   Once you have completed the "Asyndeton / Connecting Word" step, the "Download Annotations for Current Sentence" button (at the very bottom) becomes active.
*   Click this button to save all your annotations for the currently selected sentence.
*   You will be prompted to enter a filename. The file will be saved with a `.cex` extension, containing your annotations in a delimited text format.

**General Workflow:**
The app is designed to be used sequentially. Completing earlier annotation steps often unlocks or enables later ones. If a section or control seems inactive, ensure you've completed the necessary preceding steps.
