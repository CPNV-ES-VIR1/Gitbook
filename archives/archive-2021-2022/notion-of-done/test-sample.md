# Test sample

```
//Test template
test('[functionTested]_[Scenario]_[ResultExpected]', () => {
    //given

    //when
    
    //then
})
```

```
//Test sample
test('updateCart_UpdateExistingCartItemQuantity_Success', () => {
    //given
    let item1 = new CartItem(1,"Iphone 27",2,10);
    let cart = new Cart([item1]);

    let itemToUpdate = new CartItem(1, "Iphone 27"  ,1,10);
    let expectedItems = [itemToUpdate];
    let expectedTotalPrice = 10;

    //when
    cart.updateCart(expectedItems);

    //then
    let actualItems = cart.items;
    for (let i = 0 ; i <= expectedItems.length ; i++)
    {
        expect(expectedItems[i]).toEqual(actualItems[i]);
    }
    expect(expectedTotalPrice).toEqual(cart.totalPrice);
})
```

```
//Test sample with exception
test('items_EmptyCart_ThrowException', () => {
    //given
    let cart = new Cart(null);

    //when
    expect(() => cart.items).toThrow(EmptyCartException);

    //then
    //Exception is thrown
})
```
