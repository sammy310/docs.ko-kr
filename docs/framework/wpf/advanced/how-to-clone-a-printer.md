---
title: '방법: 프린터 복제'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: 09a445da068f0141b9526e0228df8be0105498c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310462"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="cb16e-102">방법: 프린터 복제</span><span class="sxs-lookup"><span data-stu-id="cb16e-102">How to: Clone a Printer</span></span>
<span data-ttu-id="cb16e-103">대부분의 비즈니스, 어느 시점에서 구입 동일한 모델의 여러 프린터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="cb16e-104">일반적으로 이러한 모든 설치 되며 실제로 동일한 구성 설정을 사용 하 여.</span><span class="sxs-lookup"><span data-stu-id="cb16e-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="cb16e-105">각 프린터 설치 시간이 오래 걸릴 수 및 오류가 발생 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="cb16e-106">합니다 <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> 네임 스페이스 및 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> Microsoft.NET Framework를 사용 하 여 노출 되는 클래스를 사용 하면 기존 인쇄 큐에서 개수에 관계 없이 복제 되는 추가 인쇄 대기열을 즉시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb16e-107">예제</span><span class="sxs-lookup"><span data-stu-id="cb16e-107">Example</span></span>  
 <span data-ttu-id="cb16e-108">아래 예제에서는 기존 인쇄 큐에서 두 번째 인쇄 대기열 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="cb16e-109">두 번째 다른 첫 번째에서 이름, 위치, 포트 및 공유 상태에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="cb16e-110">이 작업을 수행 하는 것에 대 한 주요 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="cb16e-111">만들기는 <xref:System.Printing.PrintQueue> 복제할 하려는 기존 프린터에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="cb16e-112">만들기는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> 에서 합니다 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> 의 <xref:System.Printing.PrintQueue>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="cb16e-113">합니다 <xref:System.Collections.DictionaryEntry.Value%2A> 이 사전의 각 항목의 속성에서 파생 된 형식의 개체인 <xref:System.Printing.IndexedProperties.PrintProperty>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="cb16e-114">이 사전에 있는 항목의 값을 설정 하는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="cb16e-115">사전의 사용 하 여 **제거할** 및 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> 방법 항목을 제거 하 고 원하는 값을 사용 하 여 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="cb16e-116">사전의 사용 하 여 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cb16e-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="cb16e-117">아래 예제에서는 두 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="cb16e-118">만들기를 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체 및 설정 해당 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "IsShared" 하 고 <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> 에 `true`.</span><span class="sxs-lookup"><span data-stu-id="cb16e-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="cb16e-119">사용 된 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체의 값으로는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "IsShared" 항목.</span><span class="sxs-lookup"><span data-stu-id="cb16e-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="cb16e-120">만들기는 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체 및 설정 해당 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "ShareName" 하 고 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 를 적절 한 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="cb16e-121">사용 된 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체의 값으로는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "ShareName" 항목.</span><span class="sxs-lookup"><span data-stu-id="cb16e-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="cb16e-122">만들면 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체 및 설정 해당 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "위치" 및 해당 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 를 적절 한 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="cb16e-123">두 번째를 사용 하 여 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체의 값으로는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "위치" 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="cb16e-124">배열을 만들어 <xref:System.String>s입니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="cb16e-125">각 항목에는 서버에서 포트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="cb16e-126">사용 하 여 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 새 값으로 새 프린터를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="cb16e-127">예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb16e-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="cb16e-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="cb16e-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="cb16e-129">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="cb16e-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="cb16e-130">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="cb16e-130">Printing Overview</span></span>](printing-overview.md)
