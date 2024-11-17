def scrape_amazon_product(url):
    headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/118.0.0.0 Safari/537.36'}
    response =('url, headers=headers')
    soup =  (response.content, 'html.parser')

    # Extract product title
    title = soup.find('span', id='productTitle').text.strip()

    # Extract product price
    price = soup.find('span', id="priceblock_ourprice").text.strip()

    # Extract product rating
    rating = soup.find('span', id="acrOverallStarRating").text.strip()

    # Extract product reviews
    reviews = soup.find('span', id="acrCustomerReviewText").text.strip()

    # Print the extracted data
    print("Title:", title)
    print("Price:", price)
    print("Rating:", rating)
    print("Reviews:", reviews)

# Replace with the actual product URL
url = "https://www.amazon.com/Apple-Watch-Series-8-GPS-45mm-Midnight-Aluminum-Case-Midnight-Sport-Band/dp/B0B3G9J94B"
scrape_amazon_product(url)
