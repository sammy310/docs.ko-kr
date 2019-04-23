---
title: null 허용 구조적 형식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 632b092e1d0d99a2a40cc3cd4b323e234de6232b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127857"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="132c9-102">null 허용 구조적 형식(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="132c9-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="132c9-103">구조적 형식의 `null` 인스턴스는 존재하지 않는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="132c9-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="132c9-104">이는 모든 속성에 `null` 값이 있는 기존 인스턴스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="132c9-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="132c9-105">이 항목에서는 어떤 형식이 nullable이고 어떤 코드 패턴이 구조적 nullable 형식의 `null` 인스턴스를 생성하는지를 비롯하여 구조적 nullable형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="132c9-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="132c9-106">구조적 Nullable 형식의 종류</span><span class="sxs-lookup"><span data-stu-id="132c9-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="132c9-107">구조적 nullable 형식에는 세 가지 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="132c9-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="132c9-108">행 형식</span><span class="sxs-lookup"><span data-stu-id="132c9-108">Row types.</span></span>  
  
-   <span data-ttu-id="132c9-109">복합 형식</span><span class="sxs-lookup"><span data-stu-id="132c9-109">Complex types.</span></span>  
  
-   <span data-ttu-id="132c9-110">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="132c9-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="132c9-111">구조적 형식의 Null 인스턴스를 생성하는 코드 패턴</span><span class="sxs-lookup"><span data-stu-id="132c9-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="132c9-112">다음 시나리오에서는 `null` 인스턴스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="132c9-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="132c9-113">`null`을 구조적 형식으로 모양 결정:</span><span class="sxs-lookup"><span data-stu-id="132c9-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="132c9-114">기본 형식을 파생 형식으로 업캐스트:</span><span class="sxs-lookup"><span data-stu-id="132c9-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="132c9-115">False 조건에 대한 외부 조인:</span><span class="sxs-lookup"><span data-stu-id="132c9-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="132c9-116">--또는</span><span class="sxs-lookup"><span data-stu-id="132c9-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="132c9-117">--또는</span><span class="sxs-lookup"><span data-stu-id="132c9-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="132c9-118">`null` 참조 역참조:</span><span class="sxs-lookup"><span data-stu-id="132c9-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="132c9-119">빈 컬렉션에서 ANYELEMENT 가져오기:</span><span class="sxs-lookup"><span data-stu-id="132c9-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="132c9-120">구조적 형식의 `null` 인스턴스 확인:</span><span class="sxs-lookup"><span data-stu-id="132c9-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="132c9-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="132c9-121">See also</span></span>

- [<span data-ttu-id="132c9-122">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="132c9-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
