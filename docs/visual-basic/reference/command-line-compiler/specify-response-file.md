---
description: '자세한 정보: @(지시 파일 지정)(Visual Basic)'
title: '@(지시 파일 지정)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 7a28be0d0bf6da177d9cfe85ecdb40eccf8a339f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473916"
---
# <a name="-specify-response-file-visual-basic"></a>@(지시 파일 지정)(Visual Basic)

컴파일러 옵션과 컴파일할 소스 코드 파일이 포함된 파일을 지정합니다.

## <a name="syntax"></a>구문

```console
@response_file
```

## <a name="arguments"></a>인수

`response_file`  
필수 요소. 컴파일러 옵션이나 컴파일할 소스 코드 파일이 나열된 파일입니다. 공백이 있으면 파일 이름을 따옴표(" ")로 묶습니다.

## <a name="remarks"></a>설명

컴파일러는 지시 파일에 지정된 컴파일러 옵션 및 소스 코드 파일을 명령줄에 지정된 것처럼 처리합니다.

컴파일에 지시 파일을 둘 이상 지정하려면 다음과 같이 여러 지시 파일 옵션을 지정합니다.

```console
@file1.rsp @file2.rsp
```

지시 파일에서 여러 컴파일러 옵션과 소스 코드 파일이 한 줄에 나타날 수 있습니다. 단일 컴파일러 옵션 사양은 한 줄에 표시되어야 합니다(여러 줄에 걸쳐 있을 수 없음). 지시 파일은 `#` 기호로 시작하는 주석을 포함할 수 있습니다.

명령줄에 지정된 옵션을 하나 이상의 지시 파일에 지정된 옵션과 결합할 수 있습니다. 명령 옵션이 발견되면 컴파일러에서 처리합니다. 따라서, 명령줄 인수는 지시 파일에서 이전에 나열된 옵션을 재정의할 수 있습니다. 반대로 지시 파일의 옵션은 명령줄 또는 다른 지시 파일에서 이전에 나열된 옵션을 재정의합니다.

Visual Basic에서는 Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일을 제공합니다. Vbc.rsp 파일은 `-noconfig` 옵션을 사용하지 않는 한 기본적으로 포함되어 있습니다. 자세한 내용은 [-noconfig](noconfig.md)를 참조하세요.

> [!NOTE]
> Visual Studio 개발 환경 내에서는 `@` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.

## <a name="example"></a>예제

다음 줄은 샘플 지시 파일에서 가져온 것입니다.

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a>예제

다음 예제에서는 `File1.rsp`이라는 지시 파일에 `@` 옵션을 사용하는 방법을 보여 줍니다.

```console
vbc @file1.rsp
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-noconfig](noconfig.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
