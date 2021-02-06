---
description: '자세한 정보: 방법: 기존 서비스 계약을 사용 하는 워크플로 서비스 만들기'
title: '방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 0a31f0f4e205c72b857b59726437e896a7c68231
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631257"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="1ac19-103">방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="1ac19-103">How to: Create a workflow service that consumes an existing service contract</span></span>

<span data-ttu-id="1ac19-104">.NET Framework 4.5는 계약 중심 워크플로 개발의 형태로 웹 서비스와 워크플로 간에 더 나은 통합 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-104">.NET Framework 4.5 features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="1ac19-105">계약 중심 워크플로 개발 도구를 사용하면 코드에서 계약을 먼저 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-105">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="1ac19-106">그러면 이 도구는 계약의 작업을 위해 도구 상자에 활동 템플릿을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-106">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ac19-107">이 항목에서는 계약 중심 워크플로 서비스를 만들기 위한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-107">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="1ac19-108">계약 중심 워크플로 서비스 개발에 대 한 자세한 내용은 [첫 번째 워크플로 서비스 개발 계약](contract-first-workflow-service-development.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ac19-108">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="1ac19-109">워크플로 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="1ac19-109">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="1ac19-110">Visual Studio에서 **파일**, **새 프로젝트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-110">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="1ac19-111">**템플릿** 트리의 **c #** 노드 아래에서 **wcf** 노드를 선택 하 고 **wcf 워크플로 서비스 응용 프로그램** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-111">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="1ac19-112">새 프로젝트의 이름을로 `ContractFirst` 하 고 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-112">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="1ac19-113">서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="1ac19-113">Creating the service contract</span></span>  
  
1. <span data-ttu-id="1ac19-114">**솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 항목**...을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-114">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="1ac19-115">왼쪽에서 **코드** 노드를 선택 하 고 오른쪽의 **클래스** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-115">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="1ac19-116">새 클래스의 이름을로 `IBookService` , **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-116">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="1ac19-117">표시되는 코드 창의 맨 위에서 `System.Servicemodel`에 Using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-117">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="1ac19-118">샘플 클래스 정의를 다음과 같은 인터페이스 정의로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-118">Change the sample class definition to the following interface definition.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. <span data-ttu-id="1ac19-119">**Ctrl + Shift + B** 를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-119">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="1ac19-120">서비스 계약 가져오기</span><span class="sxs-lookup"><span data-stu-id="1ac19-120">Importing the service contract</span></span>  
  
1. <span data-ttu-id="1ac19-121">**솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **서비스 계약 가져오기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-121">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="1ac19-122">에서 **\<Current Project>** 모든 하위 노드를 열고 **Ibookservice** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-122">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="1ac19-123">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-123">Click **OK**.</span></span>  
  
2. <span data-ttu-id="1ac19-124">작업이 성공적으로 완료되었음을 알리는 대화 상자가 열리고 프로젝트가 빌드된 후 생성된 활동이 도구 상자에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-124">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="1ac19-125">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-125">Click **OK**.</span></span>  
  
3. <span data-ttu-id="1ac19-126">가져온 활동이 도구 상자에 표시 되도록 **Ctrl + Shift + B** 를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-126">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="1ac19-127">**솔루션 탐색기** 에서 .xamlx을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-127">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="1ac19-128">워크플로 서비스가 디자이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-128">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="1ac19-129">**Sequence** 활동을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-129">Select the **Sequence** activity.</span></span> <span data-ttu-id="1ac19-130">속성 창 **에서 ...**</span><span class="sxs-lookup"><span data-stu-id="1ac19-130">In the Properties window, click the **…**</span></span> <span data-ttu-id="1ac19-131">**구현 된 Edcontract** 속성의 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-131">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="1ac19-132">표시 되는 **형식 컬렉션 편집기** 창에서 **형식** 드롭다운을 클릭 하 고 **형식 찾아보기** ...를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-132">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="1ac19-133">항목을 찾아서 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-133">entry.</span></span> <span data-ttu-id="1ac19-134">**.Net 형식 찾아보기 및 선택** 대화 상자의 아래에서 **\<Current Project>** 모든 하위 노드를 열고 **ibookservice** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-134">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="1ac19-135">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-135">Click **OK**.</span></span> <span data-ttu-id="1ac19-136">**형식 컬렉션 편집기** 대화 상자에서 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-136">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="1ac19-137">**ReceiveRequest** 및 **sendresponse** 활동을 선택 하 고 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-137">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="1ac19-138">도구 상자에서 **Buy_ReceiveAndSendReply** 및 **Checkout_Receive** 활동을 **순차 서비스** 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ac19-138">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
