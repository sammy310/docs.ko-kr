---
description: '자세히 알아보기: XML을 사용 하 여 코드 문서화 (Visual Basic)'
title: XML로 코드 문서화
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: b554007bdd5183d0d92dc7ff62d08885f4b7f486
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476009"
---
# <a name="document-your-code-with-xml-visual-basic"></a>코드를 XML로 문서화(Visual Basic)

Visual Basic에서 XML을 사용 하 여 코드를 문서화할 수 있습니다.

## <a name="xml-documentation-comments"></a>XML 문서 주석

Visual Basic는 프로젝트에 대 한 XML 문서를 자동으로 만드는 쉬운 방법을 제공 합니다. 형식 및 멤버에 대해 XML 기본 구조를 자동으로 생성 한 다음 요약, 각 매개 변수에 대 한 설명 설명서 및 기타 설명을 제공할 수 있습니다. 적절 한 설정을 사용 하 여 XML 문서를 프로젝트와 동일한 루트 파일 이름으로 XML 파일에 자동으로 내보냅니다. 자세한 내용은 [-doc](../../reference/command-line-compiler/doc.md)를 참조하세요.

XML 파일을 사용 하거나 XML로 조작할 수 있습니다. 이 파일은 프로젝트의 출력 .exe 또는 .dll 파일과 같은 디렉터리에 있습니다.

XML 문서는 `'''`로 시작합니다. 이러한 주석의 처리에는 몇 가지 제한이 있습니다.

- 문서는 잘 구성된 XML이어야 합니다. XML의 형식이 잘못 된 경우 경고가 생성 되 고 설명서 파일에 오류가 발생 했다는 설명이 포함 되어 있습니다.

- 개발자는 각자 고유한 태그 집합을 만들 수 있습니다. 권장 태그 집합이 있습니다 ( [XML 주석 태그](../../language-reference/xmldoc/index.md)참조). 권장 태그 중 일부는 특별한 의미가 있습니다.

  - \<param> 태그는 매개 변수를 설명하는 데 사용됩니다. 사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다. 확인에 실패하면 컴파일러가 경고를 실행합니다.

  - `cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다. 컴파일러에서 이 코드 요소가 있는지 확인합니다. 확인에 실패하면 컴파일러가 경고를 실행합니다. 또한 컴파일러는 `Imports` 특성에 설명 된 형식을 찾을 때 문을 고려 합니다 `cref` .

  - \<summary>태그는 Visual Studio의 IntelliSense에서 형식 또는 멤버에 대 한 추가 정보를 표시 하는 데 사용 됩니다.

## <a name="related-sections"></a>관련 단원

문서 주석을 사용 하 여 XML 파일을 만드는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

- [-doc](../../reference/command-line-compiler/doc.md)

- [XML 주석 태그](../../language-reference/xmldoc/index.md)

- [XML 파일 처리](processing-the-xml-file.md)

- [방법: XML 설명서 만들기](how-to-create-xml-documentation.md)

- [Visual Studio의 XML 도구](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>참조

- [Visual Basic을 사용한 애플리케이션 개발](../../developing-apps/index.md)
- [Visual Basic 프로그래밍 가이드](../index.md)
