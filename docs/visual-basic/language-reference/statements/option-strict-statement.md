---
title: Option Strict 문
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: ab1094961e2bc3aed0e975e40369a5f5c1ba93eb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873135"
---
# <a name="option-strict-statement"></a>Option Strict 문

암시적 데이터 형식 변환을 확대 변환 으로만 제한 하 고 런타임에 바인딩을 허용 하지 않으며 형식을 생성 하는 암시적 형식화를 허용 하지 `Object` 않습니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`On`|선택 사항입니다. 검사를 사용 하도록 설정 `Option Strict` 합니다.|  
|`Off`|선택 사항입니다. 검사를 사용 하지 않습니다 `Option Strict` .|  
  
## <a name="remarks"></a>설명  

 `Option Strict On` `Option Strict` 파일이 파일에 표시 되 면 다음 조건으로 인해 컴파일 시간 오류가 발생 합니다.  
  
- 암시적 축소 변환  
  
- 런타임에 바인딩  
  
- `Object` 유형으로 이어지는 암시적 형식 지정  
  
> [!NOTE]
> [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)에서 설정할 수 있는 경고 구성에는 컴파일 시간 오류를 발생 시키는 세 가지 조건에 해당 하는 세 가지 설정이 있습니다. 이러한 설정을 사용 하는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 [IDE에서 경고 구성을 설정 하려면을](option-strict-statement.md#conditions) 참조 하세요.  
  
 `Option Strict Off`이 문은 연결 된 IDE 설정이 이러한 오류 또는 경고를 설정 하도록 지정 하더라도 세 가지 조건 모두에 대해 오류 및 경고 검사를 해제 합니다. `Option Strict On`문은 연결 된 IDE 설정이 이러한 오류 또는 경고를 해제 하도록 지정 하더라도 세 가지 조건 모두에 대해 오류 및 경고 검사를 설정 합니다.  
  
 사용 되는 경우 `Option Strict` 문은 파일의 다른 코드 문 앞에 나와야 합니다.  
  
 `Option Strict`를로 설정 하면 `On` Visual Basic 모든 프로그래밍 요소에 대해 데이터 형식이 지정 되었는지 확인 합니다. 데이터 형식은 명시적으로 지정 하거나 로컬 형식 유추를 사용 하 여 지정할 수 있습니다. 다음과 같은 이유로 모든 프로그래밍 요소에 대 한 데이터 형식을 지정 하는 것이 좋습니다.  
  
- 변수 및 매개 변수에 대해 IntelliSense를 지원할 수 있습니다. 이렇게 하면 코드를 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.  
  
- 컴파일러에서 형식 검사를 수행할 수 있습니다. 형식 검사를 사용 하면 형식 변환 오류로 인해 런타임에 실패할 수 있는 문을 찾을 수 있습니다. 또한 이러한 메서드를 지원 하지 않는 개체에 대 한 메서드 호출을 식별 합니다.  
  
- 코드의 실행 속도를 향상 시킵니다. 한 가지 이유는 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않는 경우 Visual Basic 컴파일러에서 해당 형식을 할당 하는 것입니다 `Object` . 컴파일된 코드는 `Object` 와 다른 데이터 형식 간에 앞뒤로 변환 해야 하므로 성능이 저하 될 수 있습니다.  
  
## <a name="implicit-narrowing-conversion-errors"></a>암시적 축소 변환 오류  

 암시적 축소 변환 오류는 축소 변환인 암시적 데이터 형식 변환이 있을 경우 발생합니다.  
  
 Visual Basic는 여러 데이터 형식을 다른 데이터 형식으로 변환할 수 있습니다. 한 데이터 형식의 값을 정밀도 나 용량이 더 적은 데이터 형식으로 변환 하는 경우 데이터 손실이 발생할 수 있습니다. 이러한 축소 변환이 실패 하면 런타임 오류가 발생 합니다. `Option Strict` 는 이러한 축소 변환을 방지할 수 있도록 컴파일 시간 알림을 사용 합니다. 자세한 내용은 [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) 및 [확대/축소 변환](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조 하세요.  
  
 오류를 일으킬 수 있는 변환에는 식에서 발생 하는 암시적 변환이 포함 됩니다. 자세한 내용은 다음 항목을 참조하세요.  
  
- [+ 연산자](../operators/addition-operator.md)  
  
- [+ = 연산자](../operators/addition-assignment-operator.md)  
  
- [\ 연산자 (Visual Basic)](../operators/integer-division-operator.md)  
  
- [/= 연산자 (Visual Basic)](../operators/floating-point-division-assignment-operator.md)  
  
- [Char 데이터 형식](../data-types/char-data-type.md)  
  
 [& 연산자](../operators/concatenation-operator.md)를 사용 하 여 문자열을 연결 하는 경우 문자열에 대 한 모든 변환이 확대 된 것으로 간주 됩니다. 따라서 이러한 변환은가 on 이더라도 암시적 축소 변환 오류를 생성 하지 않습니다 `Option Strict` .  
  
 해당 매개 변수와 다른 데이터 형식의 인수를 포함 하는 메서드를 호출 하면가 on 인 경우 축소 변환을 수행 하면 컴파일 시간 오류가 발생 `Option Strict` 합니다. 확대 변환 또는 명시적 변환을 사용 하 여 컴파일 시간 오류를 방지할 수 있습니다.  
  
 암시적 축소 변환 오류는 컬렉션의 요소에서 루프 제어 변수로의 변환을 위해 컴파일 타임에 표시 되지 않습니다 `For Each…Next` . 가 설정 된 경우에도이 오류가 발생 `Option Strict` 합니다. 자세한 내용은 [각 항목에 대 한 "축소 변환" 섹션을 참조 하세요. 다음 문](for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>런타임에 바인딩 오류  

 개체에 `Object` 형식으로 선언된 변수의 속성 또는 메서드에 할당되면 런타임에 바인딩됩니다. 자세한 내용은 [초기 바인딩 및 런타임에 바인딩](../../programming-guide/language-features/early-late-binding/index.md)을 참조 하세요.  
  
## <a name="implicit-object-type-errors"></a>암시적 개체 유형 오류  

 암시적 개체 형식 오류는 선언된 변수에 대해 적절한 형식이 유추될 수 없어 `Object`의 형식이 유추될 때 발생합니다. 주로 `As` 절을 사용하지 않고 `Dim` 문을 사용하여 변수를 선언하고, `Option Infer`가 꺼져 있는 경우 발생합니다. 자세한 내용은 [Option 유추 문](option-infer-statement.md) 및 [Visual Basic 언어 사양](../../reference/language-specification/index.md)을 참조 하세요.  
  
 메서드 매개 변수의 `As` 경우가 off 인 경우 절은 선택 사항입니다 `Option Strict` . 그러나 한 매개 변수에서 절을 사용 하는 경우 `As` 모두 해당 매개 변수를 사용 해야 합니다. `Option Strict`가 on 이면 `As` 모든 매개 변수 정의에 절이 필요 합니다.  
  
 절을 사용 하지 않고 변수를 선언 하 `As` 고로 설정 하는 경우 `Nothing` 변수의 형식은 `Object` 입니다. 이 경우 `Option Strict` 가 on이 고가 on 이면 컴파일 시간 오류가 발생 하지 않습니다 `Option Infer` . 예를 들면 `Dim something = Nothing` 입니다.  
  
### <a name="default-data-types-and-values"></a>기본 데이터 형식 및 값  

 다음 표에서는 [Dim 문에](dim-statement.md)데이터 형식 및 이니셜라이저를 지정 하는 다양 한 조합의 결과에 대해 설명 합니다.  
  
|데이터 형식 지정 여부|이니셜라이저 지정 여부|예제|결과|  
|---|---|---|---|  
|아니요|아니요|`Dim qty`|`Option Strict`가 off(기본값)이면 변수는 `Nothing`으로 설정됩니다.<br /><br /> `Option Strict`가 on이면 컴파일 시간 오류가 발생합니다.|  
|아니요|예|`Dim qty = 5`|`Option Infer`가 on(기본값)이면 변수가 이니셜라이저의 데이터 형식을 사용합니다. [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.<br /><br /> `Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.<br /><br /> `Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 시간 오류가 발생합니다.|  
|예|예|`Dim qty As Integer`|변수는 데이터 형식의 기본값으로 초기화됩니다. 자세한 내용은 [Dim 문](dim-statement.md)을 참조 하세요.|  
|예|예|`Dim qty  As Integer = 5`|이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Option Strict 문이 없는 경우  

 소스 코드에 문이 포함 되어 있지 않으면 `Option Strict` [프로젝트 디자이너 (Visual Basic)의 컴파일 페이지](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 에서 **Option strict** 설정이 사용 됩니다. **컴파일 페이지** 에는 오류를 생성 하는 조건에 대 한 추가 제어를 제공 하는 설정이 있습니다.  
  
 명령줄 컴파일러를 사용 하는 경우 [-옵션 strict](../../reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 사용 하 여에 대 한 설정을 지정할 수 있습니다 `Option Strict` .  
  
### <a name="to-set-option-strict-in-the-ide"></a>IDE에서 Option Strict를 설정 하려면  

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1. **솔루션 탐색기**에서 프로젝트를 선택 합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2. **컴파일** 탭에서 **Option Strict** 상자에 값을 설정 합니다.  
  
### <a name="to-set-warning-configurations-in-the-ide"></a><a name="conditions"></a> IDE에서 경고 구성을 설정 하려면  

 컴파일 페이지를 사용 하는 경우 문 대신 [프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 를 사용 하면 `Option Strict` 오류를 생성 하는 조건을 추가로 제어할 수 있습니다. **컴파일 페이지** 의 **경고 구성** 섹션에 `Option Strict` 는가 on 인 경우 컴파일 시간 오류를 발생 시키는 세 가지 조건에 해당 하는 설정이 있습니다. 이러한 설정은 다음과 같습니다.  
  
- **암시적 변환**  
  
- **런타임에 바인딩; 호출이 실패할 수 있음**  
  
- **암시적 형식; 개체로 간주**  
  
 **Option Strict**를 **On**으로 설정하는 경우 이러한 세 가지 경고 구성 설정은 모두 **Error**로 설정됩니다. **Option Strict**를 **Off**로 설정하는 경우 세 가지 설정은 모두 **None**으로 설정됩니다.  
  
 각 경고 구성 설정은 **None**, **Warning** 또는 **Error**로 개별적으로 변경할 수 있습니다. 세 가지 경고 구성 설정이 모두 **Error**로 설정 된 경우이 `On` 상자에 나타납니다 `Option strict` . 3 개가 모두 **없음**으로 설정 된 경우 `Off` 이 상자에 표시 됩니다. 이러한 설정의 다른 조합의 경우 **(사용자 지정)** 이 나타납니다.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>새 프로젝트에 대 한 Strict 기본 설정 옵션을 설정 하려면  

 프로젝트를 만들 때 **컴파일** 탭의 **옵션 strict** 설정이 **옵션** 대화 상자의 **option strict** 설정으로 설정 됩니다.  
  
 `Option Strict`이 대화 상자에서 설정 하려면 **도구** 메뉴에서 **옵션**을 클릭 합니다. **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다. **VB 기본값** 의 초기 기본 설정은 `Off` 입니다.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>명령줄에서 Option Strict를 설정 하려면  

 **Vbc** 명령에 [-옵션 strict](../../reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 포함 합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 축소 변환 인 암시적 형식 변환으로 인해 발생 하는 컴파일 시간 오류를 보여 줍니다. 이 범주의 오류는 **컴파일 페이지**의 **암시적 변환** 조건에 해당 합니다.  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a>예제  

 다음 예제에서는 런타임에 바인딩으로 인해 발생 하는 컴파일 시간 오류를 보여 줍니다. 이 범주의 오류는 런타임에 바인딩과 일치 합니다. **컴파일 페이지**에서 **런타임에 호출이 실패할 수** 있습니다.  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a>예제  

 다음 예제에서는의 암시적 형식으로 선언 된 변수에 의해 발생 하는 오류를 보여 줍니다 `Object` . 이 범주의 오류는 **컴파일 페이지**에서 **암시적 형식, 개체를 사용한** 조건에 해당 합니다.  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a>참조

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Option Explicit 문](option-explicit-statement.md)
- [형식 변환 함수](../functions/type-conversion-functions.md)
- [방법: 개체의 멤버에 액세스](../../programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [XML의 포함 식](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [완화된 대리자 변환](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Office 솔루션에서 런타임에 바인딩](/visualstudio/vsto/late-binding-in-office-solutions)
- [-optionstrict](../../reference/command-line-compiler/optionstrict.md)
- [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
