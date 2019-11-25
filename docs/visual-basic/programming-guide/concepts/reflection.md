---
title: 반사
ms.date: 07/20/2015
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
ms.openlocfilehash: 28f33c88f7aaaf51938a7d27fd2218a97b628acd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349274"
---
# <a name="reflection-visual-basic"></a><span data-ttu-id="09d0a-102">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09d0a-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="09d0a-103">리플렉션은 어셈블리, 모듈 및 형식을 설명하는 개체(<xref:System.Type> 형식)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="09d0a-104">리플렉션을 사용하면 동적으로 형식 인스턴스를 만들거나, 형식을 기존 개체에 바인딩하거나, 기존 개체에서 형식을 가져와 해당 메서드를 호출하거나, 필드 및 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="09d0a-105">코드에서 특성을 사용하는 경우 리플렉션은 특성에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="09d0a-106">자세한 내용은 [특성](../../../standard/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09d0a-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="09d0a-107">다음은 정적 메서드 `GetType`(`Object` 기본 클래스의 모든 형식에 상속됨)을 사용하여 변수 형식을 가져오는 간단한 리플렉션 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="09d0a-108">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="09d0a-109">다음 예제에서는 리플렉션을 사용하여 로드된 어셈블리의 전체 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="09d0a-110">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="09d0a-111">리플렉션 개요</span><span class="sxs-lookup"><span data-stu-id="09d0a-111">Reflection Overview</span></span>  
 <span data-ttu-id="09d0a-112">리플렉션은 다음과 같은 상황에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-112">Reflection is useful in the following situations:</span></span>  
  
- <span data-ttu-id="09d0a-113">프로그램 메타데이터의 특성에 액세스해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="09d0a-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="09d0a-114">자세한 내용은 [특성에 저장된 정보 검색](../../../standard/attributes/retrieving-information-stored-in-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09d0a-114">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
- <span data-ttu-id="09d0a-115">어셈블리에서 형식을 검사하고 인스턴스화하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="09d0a-115">For examining and instantiating types in an assembly.</span></span>  
  
- <span data-ttu-id="09d0a-116">런타임에 새 형식을 빌드하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="09d0a-116">For building new types at runtime.</span></span> <span data-ttu-id="09d0a-117"><xref:System.Reflection.Emit>의 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="09d0a-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
- <span data-ttu-id="09d0a-118">런타임에 바인딩을 수행하고 런타임에 생성된 형식의 메서드에 액세스하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="09d0a-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="09d0a-119">[동적으로 형식 로드 및 사용](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09d0a-119">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="09d0a-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="09d0a-120">Related Sections</span></span>  
 <span data-ttu-id="09d0a-121">추가 정보</span><span class="sxs-lookup"><span data-stu-id="09d0a-121">For more information:</span></span>  
  
- [<span data-ttu-id="09d0a-122">리플렉션</span><span class="sxs-lookup"><span data-stu-id="09d0a-122">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
- [<span data-ttu-id="09d0a-123">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="09d0a-123">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
- [<span data-ttu-id="09d0a-124">리플렉션 및 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="09d0a-124">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
- <xref:System.Reflection.Emit>  
  
- [<span data-ttu-id="09d0a-125">특성에 저장된 정보 검색</span><span class="sxs-lookup"><span data-stu-id="09d0a-125">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="09d0a-126">참조</span><span class="sxs-lookup"><span data-stu-id="09d0a-126">See also</span></span>

- [<span data-ttu-id="09d0a-127">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="09d0a-127">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="09d0a-128">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="09d0a-128">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
