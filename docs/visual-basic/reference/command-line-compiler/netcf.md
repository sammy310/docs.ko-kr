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
ms.openlocfilehash: 028fa148d0e5622648a5fdfff1789c3d0bfde057
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268287"
---
# <a name="-netcf"></a>-netcf

컴파일러가.NET Compact Framework를 대상으로 설정 합니다.

## <a name="syntax"></a>구문

```
-netcf
```

## <a name="remarks"></a>설명

`-netcf` 옵션을 사용 하면 Visual Basic 컴파일러는 전체.NET Framework 대신.NET Compact Framework를 대상으로 합니다. 전체.NET Framework에만 존재 하는 언어 기능이 비활성화 됩니다.

합니다 `-netcf` 옵션은 사용 하도록 설계 되었습니다 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)합니다. 사용 하지 않도록 설정 하는 언어 기능 `-netcf` 동일한 언어 기능을 사용 하 여 대상 파일에 없는 `-sdkpath`합니다.

> [!NOTE]
> `-netcf` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다. `-netcf` Visual Basic 장치 프로젝트를 로드 하면 옵션이 설정 됩니다.

`-netcf` 다음 언어 기능을 변경 하는 옵션:

- 합니다 [끝 \<키워드 > 문을](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 프로그램의 실행을 종료 하는 키워드를 사용 하지 않도록 설정 합니다. 다음 프로그램 없이 컴파일 및 실행 `-netcf` 컴파일 시 실패 하지만 `-netcf`합니다.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- 모든 양식에서 런타임에 바인딩을 사용할 수 없습니다. 인식 된 런타임에 바인딩된 시나리오 발생 하는 경우 컴파일 타임 오류가 생성 됩니다. 다음 프로그램 없이 컴파일 및 실행 `-netcf` 컴파일 시 실패 하지만 `-netcf`합니다.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- 합니다 [자동](../../../visual-basic/language-reference/modifiers/auto.md)를 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), 및 [유니코드](../../../visual-basic/language-reference/modifiers/unicode.md) 한정자는 사용 하지 않도록 설정 합니다. 구문의 합니다 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) 로 문 수정 됩니다 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`합니다. 다음 코드의 결과 보여 줍니다. `-netcf` 를 컴파일할 때.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Visual Basic에서 제거 된 Visual Basic 6.0 키워드를 사용 하 여 다른 오류를 생성 하면 `-netcf` 사용 됩니다. 이 키워드에 대 한 오류 메시지를 영향을 줍니다.

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

다음 코드에서는 `Myfile.vb` .NET Compact Framework를 사용 하 여 C 드라이브에.NET Compact Framework의 기본 설치 디렉터리에서 찾을 mscorlib.dll 및 Microsoft.VisualBasic.dll의 버전을 사용 합니다. 일반적으로.NET Compact Framework의 최신 버전을 사용 하면 됩니다.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
