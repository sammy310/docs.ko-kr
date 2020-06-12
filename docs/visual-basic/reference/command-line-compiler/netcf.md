---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 16fb6b3b63c848ea6c09cc18b0fcc488670f0926
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397477"
---
# <a name="-netcf"></a>-netcf

.NET Compact Framework를 대상으로 하는 컴파일러를 설정합니다.

## <a name="syntax"></a>구문

```console
-netcf
```

## <a name="remarks"></a>설명

`-netcf` 옵션을 설정하면 Visual Basic 컴파일러가 전체 .NET Framework가 아닌 .NET Compact Framework를 대상으로 합니다. 전체 .NET Framework에만 표시되는 언어 기능은 사용할 수 없습니다.

`-netcf` 옵션은 [-sdkpath](sdkpath.md)와 함께 사용하도록 설계되었습니다. `-netcf`에 의해 비활성화된 언어 기능은 `-sdkpath`를 사용하여 대상으로 지정된 파일에 없는 언어 기능과 동일합니다.

> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-netcf` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다. `-netcf` 옵션은 Visual Basic 디바이스 프로젝트가 로드될 때 설정됩니다.

`-netcf` 옵션은 다음 언어 기능을 변경합니다.

- 프로그램의 실행을 종료하는 [End \<keyword> Statement](../../language-reference/statements/end-keyword-statement.md) 키워드는 사용할 수 없습니다. 다음 프로그램은 `-netcf` 없이 컴파일되고 실행되지만 `-netcf`를 사용하면 컴파일 시간에 실패합니다.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- 런타임에 바인딩은 모든 형태에서 사용할 수 없습니다. 런타임에 바인딩 시나리오가 인식되면 컴파일 시간 오류가 생성됩니다. 다음 프로그램은 `-netcf` 없이 컴파일되고 실행되지만 `-netcf`를 사용하면 컴파일 시간에 실패합니다.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- [Auto](../../language-reference/modifiers/auto.md), [Ansi](../../language-reference/modifiers/ansi.md) 및 [Unicode](../../language-reference/modifiers/unicode.md) 한정자는 사용할 수 없습니다. [Declare Statement](../../language-reference/statements/declare-statement.md)의 구문도 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`으로 수정됩니다. 다음 코드는 컴파일에 대한 `-netcf`의 영향을 보여 줍니다.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Visual Basic에서 제거된 Visual Basic 6.0 키워드를 사용하면 `-netcf`를 사용할 때 다른 오류가 생성됩니다. 이는 다음 키워드에 대한 오류 메시지에 영향을 줍니다.

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>예제

다음 코드는 C 드라이브의 .NET Compact Framework 기본 설치 디렉터리에 있는 mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 사용하여 .NET Compact Framework로 `Myfile.vb`를 컴파일합니다. 일반적으로 최신 버전의 .NET Compact Framework를 사용합니다.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [-sdkpath](sdkpath.md)
