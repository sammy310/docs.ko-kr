---
description: '자세히 알아보기: BC36593: 형식의 식은 <type> 쿼리할 수 없습니다.'
title: <type> 형식의 식은 쿼리할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: b2fc6c81ee34c1f8e251ac65ba582fde1c6a7b9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796355"
---
# <a name="bc36593-expression-of-type-type-is-not-queryable"></a>BC36593: 형식의 식은 \<type> 쿼리할 수 없습니다.

형식의 식은 \<type> 쿼리할 수 없습니다. LINQ 공급자에 대 한 어셈블리 참조 및/또는 네임 스페이스 가져오기가 누락 되지 않았는지 확인 합니다.

 쿼리 가능한 형식은 <xref:System.Linq> , <xref:System.Data.Linq> 및 네임 스페이스에 정의 됩니다 <xref:System.Xml.Linq> . LINQ 쿼리를 수행 하려면 이러한 네임 스페이스를 하나 이상 가져와야 합니다.

 네임 스페이스를 사용 하면 <xref:System.Linq> LINQ를 사용 하 여 컬렉션 및 배열과 같은 개체를 쿼리할 수 있습니다.

 네임 스페이스를 사용 하면 <xref:System.Data.Linq> LINQ를 사용 하 여 ADO.NET 데이터 집합 및 SQL Server 데이터베이스를 쿼리할 수 있습니다.

 네임 스페이스를 사용 하면 <xref:System.Xml.Linq> LINQ를 사용 하 여 xml을 쿼리하고 Visual Basic에서 xml 기능을 사용할 수 있습니다.

 **오류 ID:** BC36593

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. `Import` <xref:System.Linq> , 또는 네임 스페이스에 대 한 문을 <xref:System.Data.Linq> <xref:System.Xml.Linq> 코드 파일에 추가 합니다. 프로젝트 디자이너의 **참조** 페이지 (**My project**)를 사용 하 여 프로젝트에 대 한 네임 스페이스를 가져올 수도 있습니다.

2. 쿼리의 원본으로 식별 한 형식이 쿼리 가능한 형식 인지 확인 합니다. 즉, 또는을 구현 하는 형식입니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.IQueryable%601> .

## <a name="see-also"></a>참고 항목

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../programming-guide/language-features/linq/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
- [참조 및 Imports 문](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports 문(.NET 네임스페이스 및 형식)](../statements/imports-statement-net-namespace-and-type.md)
- [참조 페이지, 프로젝트 디자이너(Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
