---
title: '방법: XML 설명서 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 1421cc85beba42b3cf3656c34b1d02347fbaf164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403241"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>방법: Visual Basic에서 XML 문서 만들기

이 예제에서는 코드에 XML 문서 주석을 추가 하는 방법을 보여 줍니다.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a>형식 또는 멤버에 대 한 XML 문서를 만들려면

1. **코드 편집기**에서 문서를 만들 형식 또는 멤버 위의 줄에 커서를 놓습니다.

2. `'''`(세 개의 작은 따옴표)를 입력 합니다.

    형식 또는 멤버에 대 한 XML 뼈대가 **코드 편집기**에 추가 됩니다.

3. 적절 한 태그 사이에 설명 정보를 추가 합니다.

    > [!NOTE]
    > XML 문서 블록 내에 줄을 추가 하는 경우 각 줄은로 시작 해야 합니다 `'''` .

4. 형식 또는 멤버를 사용 하는 코드를 새 XML 문서 주석과 함께 추가 합니다.

    IntelliSense는 \<summary> 형식 또는 멤버에 대 한 태그의 텍스트를 표시 합니다.

5. 코드를 컴파일하여 문서 주석을 포함 하는 XML 파일을 생성 합니다. 자세한 내용은 [-doc](../../reference/command-line-compiler/doc.md)를 참조하세요.

## <a name="see-also"></a>참조

- [코드를 XML로 문서화](documenting-your-code-with-xml.md)
- [XML 주석 태그](../../language-reference/xmldoc/index.md)
- [-doc](../../reference/command-line-compiler/doc.md)
