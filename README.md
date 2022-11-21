
Automating Amazon

Providing the URL of amazon to the cypress tool, Opening the website after clicking on the URl it will click on the search box and will type the product as per our requirement and it will click on the search button, providing more specification about the product as per the requirement like( Products under 1000, today's deal, brand.. etc ) and it will click on the checkbox button. After clicking on the checkbox buton it will show the products as per our requirement, clicking on the product we want it will click on the Add-to-cart button and the product will get added to the cart




## Installation

Install Cypress via npm;

 Switch to your project directory

    cd /your/project/path  

 This will install Cypress locally as a dev dependency for your project.
      
    npm install cypress --save-dev 

## Opening cypress application

    npx cypress open


## Running Tests

To run tests, run the following command

```bash
  npm run test
```


## Usage/Examples

it will automatically open the link we have provided, instead of amazon.in we can open any link just by providing the URL

    describe('Amazon', () => {

     it('amazon assertion test', () => {

     cy.visit('https://amazon.in')
    
  
     })

    })


## Deployment

It will interact with the checkbox button

    describe('Amazon', () => {
     it('amazon assertion test', () => {
    cy.visit('https://amazon.in')
    
    cy.get('.nav-search-field').click().type('Boat headphones')

    cy.get('#nav-search-submit-text').click()

    cy.xpath("//span[text()='3.5 mm Jack']/preceding-sibling::div/child::label/child::i['a-icon a-icon-checkbox']").click()
    
    cy.xpath("//span[text()='Top Brands']/preceding-sibling::div/child::label/child::i").click()
    
    cy.xpath("//span[text()='Newly Launched Noise Two On-Ear Headphones with 50 Hours Playtime, Low Latency(up to 40ms), 4 Play Modes, Dual Pairing, BT v5.3 (Calm White)']/parent::a").invoke('removeAttr', 'target').click()

    cy.get("#add-to-cart-button[value='Add to Cart']").click({force:true})

     })

    })
