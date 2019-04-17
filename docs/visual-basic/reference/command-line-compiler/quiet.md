---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612591"
---
# <a name="-quiet"></a>-quiet

컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.

## <a name="syntax"></a>구문

```
-quiet
```

## <a name="remarks"></a>설명

기본적으로 `-quiet`은 적용되지 않습니다. 컴파일러에서 구문 관련 오류 또는 경고를 보고, 소스 코드에서 줄도 출력 합니다. 컴파일러 출력을 구문 분석 하는 응용 프로그램에 대 한 진단만 텍스트를 출력 하도록 컴파일러에 대 한 편리한 수 있습니다.

다음 예에서 `Module1` 없이 컴파일한 경우 소스 코드를 포함 하는 오류 출력 `-quiet`합니다.

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

출력:

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

사용 하 여 컴파일된 `-quiet`, 컴파일러가 다음만 출력 합니다.

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> `-quiet` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.

## <a name="example"></a>예제

다음 코드에서는 `T2.vb` 컴파일러 구문 관련 진단에 대 한 코드를 표시 하지 않습니다.

```
vbc -quiet t2.vb
```

## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
