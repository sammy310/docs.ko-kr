---
title: '#warning - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 38c3807a696599390667060d3bf374c68845fed0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715066"
---
# <a name="warning-c-reference"></a>#warning(C# 참조)
`#warning`을 사용하면 코드의 특정 위치에서 [CS1030](../../misc/cs1030.md) 수준 1 컴파일러 경고를 생성할 수 있습니다. 예들 들어 다음과 같습니다.  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>설명
 `#warning`은 일반적으로 조건부 지시문에 사용됩니다. [#error](./preprocessor-error.md)를 사용하여 사용자 정의 오류를 생성할 수도 있습니다.  
  
## <a name="example"></a>예제  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 전처리기 지시문](./index.md)
