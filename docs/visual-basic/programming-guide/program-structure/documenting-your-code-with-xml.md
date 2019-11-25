---
title: 코드를 XML로 문서화
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347450"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>코드를 XML로 문서화(Visual Basic)

In Visual Basic, you can document your code using XML

## <a name="xml-documentation-comments"></a>XML 문서 주석

Visual Basic provides an easy way to automatically create XML documentation for projects. You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks. With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension. 자세한 내용은 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)를 참조하세요.

The XML file can be consumed or otherwise manipulated as XML. This file is located in the same directory as the output .exe or .dll file of your project.

XML documentation starts with `'''`. 이러한 주석의 처리에는 몇 가지 제한이 있습니다.

- 문서는 잘 구성된 XML이어야 합니다. If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.

- 개발자는 각자 고유한 태그 집합을 만들 수 있습니다. There is a recommended set of tags (see "Related Sections" in this topic). 권장 태그 중 일부는 특별한 의미가 있습니다.

  - \<param> 태그는 매개 변수를 설명하는 데 사용됩니다. 사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다. If the verification fails, the compiler issues a warning.

  - `cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다. 컴파일러에서 이 코드 요소가 있는지 확인합니다. If the verification fails, the compiler issues a warning. The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.

  - The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.

## <a name="related-sections"></a>관련 단원

For details on creating an XML file with documentation comments, see the following topics:

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)

- [XML 파일 처리](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Visual Studio의 XML 도구](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>참조

- [Visual Basic을 사용한 애플리케이션 개발](../../../visual-basic/developing-apps/index.md)
- [Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md)
