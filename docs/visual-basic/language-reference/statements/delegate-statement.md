---
title: Delegate 문
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 662d2c3c0767adfe406e0a6f1b1e6dccd704e795
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354070"
---
# <a name="delegate-statement"></a>Delegate 문
Used to declare a delegate. A delegate is a reference type that refers to a `Shared` method of a type or to an instance method of an object. Any procedure with matching parameter and return types can be used to create an instance of this delegate class. The procedure can then later be invoked by means of the delegate instance.  
  
## <a name="syntax"></a>구문  
  
```vb  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attrlist`|(선택 사항) List of attributes that apply to this delegate. 여러 특성은 쉼표로 구분합니다. You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").|  
|`accessmodifier`|(선택 사항) Specifies what code can access the delegate. 다음 중 하나일 수 있습니다.<br /><br /> - [Public](../../../visual-basic/language-reference/modifiers/public.md). Any code that can access the element that declares the delegate can access it.<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md). Only code within the delegate's class or a derived class can access it.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Only code within the same assembly can access the delegate.<br />- [Private](../../../visual-basic/language-reference/modifiers/private.md). Only code within the element that declares the delegate can access it.<br /><br /> - [Protected Friend](../../language-reference/modifiers/protected-friend.md) Only code within the delegate's class, a derived class, or the same assembly can access the delegate. <br />- [Private Protected](../../language-reference/modifiers/private-protected.md) Only code within the delegate's class or in a derived class in the same assembly can access the delegate. |  
|`Shadows`|(선택 사항) Indicates that this delegate redeclares and hides an identically named programming element, or set of overloaded elements, in a base class. 모든 종류의 선언된 요소를 다른 종류로 섀도잉할 수 있습니다.<br /><br /> 섀도잉된 요소는 섀도잉 요소에 액세스할 수 없는 위치를 제외하고 해당 요소를 섀도잉하는 파생 클래스 내에서 사용할 수 없습니다. For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.|  
|`Sub`|Optional, but either `Sub` or `Function` must appear. Declares this procedure as a delegate `Sub` procedure that does not return a value.|  
|`Function`|Optional, but either `Sub` or `Function` must appear. Declares this procedure as a delegate `Function` procedure that returns a value.|  
|`name`|필수 요소. Name of the delegate type; follows standard variable naming conventions.|  
|`typeparamlist`|(선택 사항) List of type parameters for this delegate. Multiple type parameters are separated by commas. Optionally, each type parameter can be declared variant by using `In` and `Out` generic modifiers. You must enclose the [Type List](../../../visual-basic/language-reference/statements/type-list.md) in parentheses and introduce it with the `Of` keyword.|  
|`parameterlist`|(선택 사항) List of parameters that are passed to the procedure when it is called. You must enclose the [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) in parentheses.|  
|`type`|Required if you specify a `Function` procedure. Data type of the return value.|  
  
## <a name="remarks"></a>주의  
 The `Delegate` statement defines the parameter and return types of a delegate class. Any procedure with matching parameters and return types can be used to create an instance of this delegate class. The procedure can then later be invoked by means of the delegate instance, by calling the delegate's `Invoke` method.  
  
 Delegates can be declared at the namespace, module, class, or structure level, but not within a procedure.  
  
 각 대리자 클래스는 개체 메서드의 사양이 전달되는 생성자를 정의합니다. 대리자 생성자에 대한 인수는 메서드 또는 람다 식에 대한 참조여야 합니다.  
  
 메서드에 대한 참조를 지정하려면 다음 구문을 사용합니다.  
  
 `AddressOf` [`expression`.]`methodname`  
  
 `expression`의 컴파일 타임 형식은 해당 시그니처가 대리자 클래스의 시그니처와 일치하는 지정된 이름의 메서드를 포함하는 클래스 또는 인터페이스의 이름이어야 합니다. `methodname`은 공유 메서드이거나 인스턴스 메서드일 수 있습니다. `methodname`은 클래스의 기본 메서드에 대해 대리자를 만들더라도 선택 사항이 아닙니다.  
  
 람다 식을 지정하려면 다음 구문을 사용합니다.  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 함수의 시그니처는 대리자 형식의 시그니처와 일치해야 합니다. 람다 식에 대한 자세한 내용은 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
 대리자에 대한 자세한 내용은 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 The following example uses the `Delegate` statement to declare a delegate for operating on two numbers and returning a number. The `DelegateTest` method takes an instance of a delegate of this type and uses it to operate on pairs of numbers.  
  
 [!code-vb[VbVbalrDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>참조

- [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [공 분산 및 반공 분산](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
