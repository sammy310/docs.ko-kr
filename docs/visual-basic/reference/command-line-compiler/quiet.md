---
description: '자세한 정보: -quiet'
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
ms.openlocfilehash: 23e1b6472e80ac6ca2ecea5c4390b43722ccebb6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432730"
---
# <a name="-quiet"></a>-quiet

컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.

## <a name="syntax"></a>구문

```console
-quiet
```

## <a name="remarks"></a>설명

기본적으로 `-quiet`은 적용되지 않습니다. 컴파일러가 구문 관련 오류 또는 경고를 보고하면 소스 코드에서 줄도 출력합니다. 컴파일러 출력을 구문 분석하는 애플리케이션의 경우 컴파일러에서 진단 텍스트만 출력하는 것이 더 편리할 수 있습니다.

다음 예제에서 `Module1`은 `-quiet` 없이 컴파일될 때 소스 코드가 포함된 오류를 출력합니다.

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

`-quiet`로 컴파일된 컴파일러는 다음 항목만 출력합니다.

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-quiet` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.

## <a name="example"></a>예제

다음 코드는 `T2.vb`를 컴파일하고 구문 관련 컴파일러 진단을 위한 코드를 표시하지 않습니다.

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
