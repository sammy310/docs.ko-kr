---
title: <permission> - C# 프로그래밍 가이드
description: XML <permission> 태그에 대해 알아봅니다. 이 태그를 사용하면 멤버의 액세스를 문서화할 수 있고, PermissionSet 클래스를 사용하면 멤버에 대한 액세스를 지정할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381725"
---
# <a name="permission-c-programming-guide"></a>\<permission>(C# 프로그래밍 가이드)

## <a name="syntax"></a>구문

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a>매개 변수

- cref = " `member`"

  현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다. 컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다. *member*는 큰따옴표(“ ”)로 묶어야 합니다.

  제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [cref 특성](./cref-attribute.md)을 참조하세요.

- `description`

  멤버 액세스 권한에 대한 설명입니다.

## <a name="remarks"></a>설명

`<permission>` 태그를 사용하면 멤버 액세스 권한을 문서화할 수 있습니다. <xref:System.Security.PermissionSet> 클래스를 사용하면 멤버 액세스 권한을 지정할 수 있습니다.

[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.

## <a name="example"></a>예제

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [문서 주석에 대한 권장 태그](./recommended-tags-for-documentation-comments.md)
