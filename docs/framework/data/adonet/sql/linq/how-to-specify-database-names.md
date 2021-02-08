---
description: '자세한 정보: 방법: 데이터베이스 이름 지정'
title: '방법: 데이터베이스 이름 지정'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 231c78830e009ed3414609eb6dbe05c3745f3e05
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785889"
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="52c02-103">방법: 데이터베이스 이름 지정</span><span class="sxs-lookup"><span data-stu-id="52c02-103">How to: Specify Database Names</span></span>

<span data-ttu-id="52c02-104">연결에서 이름이 제공되지 않은 경우 <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> 특성의 <xref:System.Data.Linq.Mapping.DatabaseAttribute> 속성을 사용하여 데이터베이스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52c02-104">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="52c02-105">코드 샘플은 <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52c02-105">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="52c02-106">데이터베이스의 이름을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="52c02-106">To specify the name of the database</span></span>  
  
1. <span data-ttu-id="52c02-107">데이터베이스의 클래스 선언에 <xref:System.Data.Linq.Mapping.DatabaseAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52c02-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2. <span data-ttu-id="52c02-108"><xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> 특성에 <xref:System.Data.Linq.Mapping.DatabaseAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52c02-108">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3. <span data-ttu-id="52c02-109"><xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> 속성 값을 지정할 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="52c02-109">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c02-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52c02-110">See also</span></span>

- [<span data-ttu-id="52c02-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="52c02-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="52c02-112">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="52c02-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
