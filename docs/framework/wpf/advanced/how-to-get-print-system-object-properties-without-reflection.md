---
title: '방법: 리플렉션을 사용하지 않고 인쇄 시스템 개체 속성 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: bb906dafd98e75708764b5f0f009900719f6a475
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335201"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="321f1-102">방법: 리플렉션을 사용하지 않고 인쇄 시스템 개체 속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="321f1-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="321f1-103">개체의 속성 (및 해당 속성의 형식)를 항목별로 정리 하는 데 리플렉션을 사용 하면 응용 프로그램 성능이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="321f1-104"><xref:System.Printing.IndexedProperties> 네임 스페이스는 리플렉션을 사용 하 여이 정보를 가져올 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="321f1-105">예제</span><span class="sxs-lookup"><span data-stu-id="321f1-105">Example</span></span>  
 <span data-ttu-id="321f1-106">이 작업을 수행 하는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-106">The steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="321f1-107">형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-107">Create an instance of the type.</span></span> <span data-ttu-id="321f1-108">형식은 아래 예에는 <xref:System.Printing.PrintQueue> Microsoft.NET Framework 하지만 거의 동일한 코드와 함께 제공 되는 형식에서 파생 된 형식에 대해 작동 합니다 <xref:System.Printing.PrintSystemObject>합니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2. <span data-ttu-id="321f1-109">만들기는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> 형식에서 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="321f1-110">합니다 <xref:System.Collections.DictionaryEntry.Value%2A> 이 사전의 각 항목의 속성에서 파생 된 형식의 개체인 <xref:System.Printing.IndexedProperties.PrintProperty>합니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3. <span data-ttu-id="321f1-111">사전 멤버를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="321f1-112">각각에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-112">For each of them, do the following.</span></span>  
  
4. <span data-ttu-id="321f1-113">위로 캐스팅 하려면 각 항목의 값이 <xref:System.Printing.IndexedProperties.PrintProperty> 만드는 데 사용 하 고는 <xref:System.Printing.IndexedProperties.PrintProperty> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5. <span data-ttu-id="321f1-114">형식을 가져오는 합니다 <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> 각를 <xref:System.Printing.IndexedProperties.PrintProperty> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="321f1-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="321f1-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="321f1-115">See also</span></span>

- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="321f1-116">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="321f1-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="321f1-117">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="321f1-117">Printing Overview</span></span>](printing-overview.md)
