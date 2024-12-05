# Examples

## Image

![VRTASS Logo](img/vrtass.jpg){: style="float: left; margin: 3px 20px 3px 3px; width: 110px;"}
Examples are shamelessly taken from Here, There, and Everywhere, including from:
<https://github.com/james-willett/material-mkdocs-youtube-2024/>{:target="_blank"},
<https://squidfunk.github.io/mkdocs-material/>{:target="_blank"}.

## Admonitions

!!! note note
    note

!!! success "More Admonitions"
    abstract, bug, danger, example, failure, info, note, question, quote, success, tip, warning.

??? info "Collapsible Callout of Emojis"
    :airplane: :alien: :anger: :anchor:
    :angry: :astonished: :bat: :blush: :bone: :camel: :clap_tone1: :cry: :dizzy_face: 
    :disappointed: :expressionless: :face_vomiting: :fearful: 
    :flag_id: :flushed: :fork_and_knife: :grinning:
    :grin: :heart_eyes: :innocent: :joy: :kissing: :kissing_closed_eyes:
    :kissing_heart: :kissing_smiling_eyes: :laughing: :mask: :neutral_face: :ninja: :no_entry:
    :no_mouth: :partying_face: :pensive: :rage: :relaxed:
    :rofl: :sauropod: :scream: :simple-android: :sleeping: :sleepy: :slightly_smiling_face: 
    :smile: :smirk: :sneezing_face: :star: :star_and_crescent:
    :stuck_out_tongue: :stuck_out_tongue_closed_eyes:
    :stuck_out_tongue_winking_eye: :sunglasses: :upside_down_face: :weary:
    :yum: :zany_face:

## Code Blocks

### Line Numbers

```py title="add_numbers.py" linenums="1"
# Function to add two numbers
def add_two_numbers(num1, num2):
    return num1 + num2

# Example usage
result = add_two_numbers(5, 3)
print('The sum is:', result)
```

### Line Numbers and HighLight

```py title="add_numbers.py" linenums="1" hl_lines="1-3"
# Function to add two numbers
def add_two_numbers(num1, num2):
    return num1 + num2

# Example usage
result = add_two_numbers(5, 3)
print('The sum is:', result)
```

### No Line Numbers

```py title="add_numbers.py"
# Function to add two numbers
def add_two_numbers(num1, num2):
    return num1 + num2

# Example usage
result = add_two_numbers(5, 3)
print('The sum is:', result)
```

### Code Blocks in Content Tabs

=== "Bash"

    ```bash
    #!/bin/bash
    echo "Hello World"

    ```

=== "C"

    ```c title="hello.c"
    {% include "static/hello.c" %}

    ```

=== "JavaScript"

    ```js
    function main() {
        console.log("Hello world!");
    }

    main();

    ```

=== "Python"

    ```py
    def main():
        print("Hello world!")

    if __name__ == "__main__":
        main()

    ```

## Custom Variable
   {{ custom_variable }}.


## Block Quote Border

> Gressu si fontibus Phrygios audire iussa tremensque regis. 
> quaesitae innixa, rebus portenditur, adhuc
> alii reges quam facto illud iuvenci. Fuerim nobiliumque, mota fratrum: dives
> raptamque fuga inmensum movent nece faciemque non.

## List
* Level 1
    * Level 2
        * Level 3
            * Level 4

## Diagrams

### Flow Chart

```mermaid
graph LR
  A[Start] --> B{Failure?};
  B -->|Yes| C[Investigate...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Success!];

```

### Sequence Diagram

```mermaid
sequenceDiagram
  autonumber
  Server->>Terminal: Send request
  loop Health
      Terminal->>Terminal: Check for health
  end
  Note right of Terminal: System online
  Terminal-->>Server: Everything is OK
  Terminal->>Database: Request customer data
  Database-->>Terminal: Customer data

```

### State Diagram

``` mermaid
stateDiagram-v2
  state fork_state <<fork>>
    [*] --> fork_state
    fork_state --> State2
    fork_state --> State3

    state join_state <<join>>
    State2 --> join_state
    State3 --> join_state
    join_state --> State4
    State4 --> [*]
```

Class Diagram

``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```

### Entity-Relationship Diagram

``` mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  ORDER ||--|{ LINE-ITEM : contains
  LINE-ITEM {
    string name
    int pricePerUnit
  }
  CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

??? info "REVISION: Thu 05 Dec 2024 21:00"
    <pre>
    REVISION: Thu 05 Dec 2024 21:00
    REVISION: Thu 05 Dec 2024 17:00
    REVISION: Tue 03 Dec 2024 23:00
    REVISION: Tue 03 Dec 2024 18:00
    REVISION: Tue 03 Dec 2024 11:00
    STARTING: Tue 03 Dec 2024 09:00
    </pre>

