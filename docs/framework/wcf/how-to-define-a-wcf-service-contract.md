---
title: '자습서: Windows Communication Foundation 서비스 계약 정의'
description: WCF 응용 프로그램을 만들기 시작 하는 데 도움이 되는 일련의 문서에서 서비스 계약을 정의 하는 방법에 대해 알아봅니다.
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246313"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="b4987-103">자습서: Windows Communication Foundation 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="b4987-103">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="b4987-104">이 자습서에서는 WCF (기본 Windows Communication Foundation) 응용 프로그램을 만드는 데 필요한 5 가지 작업 중 첫 번째 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-104">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="b4987-105">자습서에 대 한 개요는 [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4987-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="b4987-106">WCF 서비스를 만들 때 첫 번째 작업은 서비스 계약을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-106">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="b4987-107">서비스 계약은 서비스에서 지원하는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-107">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="b4987-108">작업은 웹 서비스 메서드로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-108">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="b4987-109">C # 또는 Visual Basic 인터페이스를 정의 하 여 서비스 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-109">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="b4987-110">인터페이스에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-110">An interface has the following characteristics:</span></span>

- <span data-ttu-id="b4987-111">인터페이스의 각 메서드는 특정 서비스 작업에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-111">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="b4987-112">각 인터페이스에 대해 특성을 적용 해야 합니다 <xref:System.ServiceModel.ServiceContractAttribute> .</span><span class="sxs-lookup"><span data-stu-id="b4987-112">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="b4987-113">각 작업/메서드에 대해 특성을 적용 해야 합니다 <xref:System.ServiceModel.OperationContractAttribute> .</span><span class="sxs-lookup"><span data-stu-id="b4987-113">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="b4987-114">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-114">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="b4987-115">**WCF 서비스 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-115">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="b4987-116">서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-116">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="b4987-117">WCF 서비스 라이브러리 프로젝트를 만들고 서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-117">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="b4987-118">관리자 권한으로 Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-118">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="b4987-119">이렇게 하려면 **시작** 메뉴에서 Visual Studio 프로그램 **을 선택 하**고  >  바로 가기 메뉴에서**관리자 권한으로 실행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-119">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="b4987-120">**WCF 서비스 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-120">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="b4987-121">**파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-121">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="b4987-122">**새 프로젝트** 대화 상자의 왼쪽에서 **Visual c #** 또는 **Visual Basic**을 확장 한 다음 **WCF** 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-122">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="b4987-123">Visual Studio는 창의 가운데 섹션에 프로젝트 템플릿 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-123">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="b4987-124">**WCF 서비스 라이브러리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-124">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="b4987-125">**WCF** 프로젝트 템플릿 범주가 표시 되지 않으면 Visual Studio의 **Windows Communication Foundation** 구성 요소를 설치 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-125">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="b4987-126">**새 프로젝트** 대화 상자에서 왼쪽에 있는 **Visual Studio 설치 관리자 열기** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-126">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="b4987-127">**개별 구성 요소** 탭을 선택한 다음 **개발 활동** 범주 아래에서 **Windows Communication Foundation** 을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-127">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="b4987-128">**수정** 을 선택 하 여 구성 요소 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-128">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="b4987-129">창의 아래쪽 섹션에서 **솔루션 이름**에 대해 시작 된 **이름** 및 *getGettingStartedLib* 를 입력 합니다. *GettingStarted*</span><span class="sxs-lookup"><span data-stu-id="b4987-129">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="b4987-130">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-130">Select **OK**.</span></span>

      <span data-ttu-id="b4987-131">Visual Studio는 *IService1.cs* (또는 Visual Basic 프로젝트용 *IService1* ), *Service1.cs* (또는 Visual Basic 프로젝트의 경우 *Service1* *App.config*) 등 세 개의 파일이 있는 프로젝트를 만듭니다. Visual Studio는 다음과 같은 파일을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-131">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="b4987-132">*IService1* 파일에는 서비스 계약의 기본 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-132">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="b4987-133">*Service1* 파일에는 서비스 계약의 기본 구현이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-133">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="b4987-134">*App.config* 파일에는 VISUAL Studio WCF 서비스 호스트 도구를 사용 하 여 기본 서비스를 로드 하는 데 필요한 구성 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-134">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="b4987-135">WCF 서비스 호스트 도구에 대 한 자세한 내용은 [Wcf 서비스 호스트 (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4987-135">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="b4987-136">Visual Basic 개발자 환경 설정을 사용 하 여 Visual Studio를 설치한 경우 솔루션이 숨겨질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-136">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="b4987-137">이 경우 **도구** 메뉴에서 **옵션** 을 선택한 다음 옵션 창에서 **프로젝트 및 솔루션**  >  **일반** 을 선택 합니다. **Options**</span><span class="sxs-lookup"><span data-stu-id="b4987-137">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="b4987-138">**솔루션 항상 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-138">Select **Always show solution**.</span></span> <span data-ttu-id="b4987-139">또한 **만들어질 때 새 프로젝트 저장** 이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-139">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="b4987-140">**솔루션 탐색기**에서 **IService1.cs** 또는 **IService1** 파일을 열고 해당 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-140">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     <span data-ttu-id="b4987-141">이 계약은 온라인 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-141">This contract defines an online calculator.</span></span> <span data-ttu-id="b4987-142">인터페이스는 `ICalculator` 특성으로 표시 됩니다 <xref:System.ServiceModel.ServiceContractAttribute> (단순화 `ServiceContract` ).</span><span class="sxs-lookup"><span data-stu-id="b4987-142">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="b4987-143">이 특성은 계약 이름을 명확 하 게 구분 하는 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-143">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="b4987-144">이 코드는 각 계산기 작업을 <xref:System.ServiceModel.OperationContractAttribute> 특성 (로 간소화)으로 표시 합니다 `OperationContract` .</span><span class="sxs-lookup"><span data-stu-id="b4987-144">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b4987-145">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b4987-145">Next steps</span></span>

<span data-ttu-id="b4987-146">이 자습서에서는 다음 작업 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-146">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="b4987-147">WCF 서비스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-147">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="b4987-148">서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-148">Define a service contract interface.</span></span>

<span data-ttu-id="b4987-149">WCF 서비스 계약을 구현 하는 방법에 대해 알아보려면 다음 자습서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4987-149">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b4987-150">자습서: WCF 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="b4987-150">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
