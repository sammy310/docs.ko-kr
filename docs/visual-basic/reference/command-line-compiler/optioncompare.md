---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ed9adc7cddd9eb204937b9819e4eeff176821e95
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400562"
---
# <a name="-optioncompare"></a>-optioncompare

문자열 비교 방법을 지정합니다.

## <a name="syntax"></a>구문

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a>설명

`-optioncompare`를 두 가지 형식 중 하나로 지정할 수 있습니다. 이진 문자열 비교를 사용하려면 `-optioncompare:binary`를 지정하고 텍스트 문자열 비교를 사용하려면 `-optioncompare:text`를 지정합니다. 기본적으로 컴파일러는 `-optioncompare:binary`를 사용합니다.

Microsoft Windows에서 현재 코드 페이지는 이진 정렬 순서를 결정합니다. 일반적인 이진 정렬 순서는 다음과 같습니다.

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

텍스트 기반 문자열 비교는 시스템의 로캘에 따라 결정되는 대/소문자 미구분 텍스트 정렬 순서를 기반으로 합니다. 일반적인 텍스트 정렬 순서는 다음과 같습니다.

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>Visual Studio IDE에서 -optioncompare를 설정하려면

1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2. **컴파일** 탭을 클릭합니다.

3. **Option Compare** 상자에서 값을 수정합니다.

### <a name="to-set--optioncompare-programmatically"></a>프로그래밍 방식으로 -optioncompare를 설정하려면

[Option Compare 문](../../language-reference/statements/option-compare-statement.md)을 참조하세요.

## <a name="example"></a>예제

다음 코드는 `ProjFile.vb`를 컴파일하고 이진 문자열 비교를 사용합니다.

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-optionexplicit](optionexplicit.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [Option Compare 문](../../language-reference/statements/option-compare-statement.md)
- [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
