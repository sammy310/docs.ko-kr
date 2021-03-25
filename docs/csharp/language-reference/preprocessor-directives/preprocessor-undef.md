---
description: '#undef - C# 참조'
title: '#undef - C# 참조'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: ecbf8f5793e70c7dd6e602a3992ee3783a76c7ca
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477982"
---
# <a name="undef-c-reference"></a>#undef(C# 참조)

`#undef`를 사용하면 기호의 정의를 해제할 수 있습니다. 그러면 [#if](./preprocessor-if.md) 지시문에서 해당 기호를 식으로 사용하여 식이 `false`로 평가됩니다.  
  
 [#define](./preprocessor-define.md) 지시문 또는 [**DefineConstants**](../compiler-options/language.md#defineconstants) 컴파일러 옵션을 사용하여 기호를 정의할 수 있습니다. `#undef` 지시문은 지시문이 아닌 문을 사용하기 전에 파일에 나와야 합니다.  
  
## <a name="example"></a>예제  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

**디버그가 정의되어 있지 않습니다.**

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 전처리기 지시문](./index.md)
