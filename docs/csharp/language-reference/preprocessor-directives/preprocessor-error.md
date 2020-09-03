---
description: '#error - C# 참조'
title: '#error - C# 참조'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138100"
---
# <a name="error-c-reference"></a>#error(C# 참조)

`#error`를 사용하면 코드의 특정 위치에서 [CS1029](../compiler-messages/cs1029.md) 사용자 정의 오류를 생성할 수 있습니다. 예:

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> 컴파일러는 `#error version`을 특수한 방식으로 처리하며 사용된 컴파일러 및 언어 버전을 포함한 메시지가 있는 컴파일러 오류 CS8304를 보고합니다.

## <a name="remarks"></a>설명

`#error`는 일반적으로 조건부 지시문에 사용됩니다.

[#warning](./preprocessor-warning.md)을 사용하여 사용자 정의 경고를 생성할 수도 있습니다.

## <a name="example"></a>예제

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 전처리기 지시문](./index.md)
