---
title: '자습서: Windows Communication Foundation 서비스 계약 정의'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929352"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="f01fa-102">자습서: Windows Communication Foundation 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="f01fa-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="f01fa-103">이 자습서에서는 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 첫 번째를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f01fa-104">자습서 개요를 참조 하세요. [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="f01fa-105">WCF 서비스를 만든 경우 첫 번째 작업 서비스 계약을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="f01fa-106">서비스 계약은 서비스가 지원하는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="f01fa-107">작업은 웹 서비스 메서드로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="f01fa-108">시각적 개체를 정의 하 여 서비스 계약을 만드는 C# 또는 Visual Basic (VB) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="f01fa-109">인터페이스에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="f01fa-110">인터페이스의 각 메서드는 특정 서비스 작업에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="f01fa-111">각 인터페이스에 대해 적용 해야 합니다는 <xref:System.ServiceModel.ServiceContractAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="f01fa-112">각 작업/메서드를 적용 해야 합니다는 <xref:System.ServiceModel.OperationContractAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="f01fa-113">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f01fa-114">만들기는 **WCF 서비스 라이브러리** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="f01fa-115">서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="f01fa-116">WCF 서비스 라이브러리 프로젝트를 만들고 서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="f01fa-117">관리자 권한으로 Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="f01fa-118">이렇게 하려면 Visual Studio 프로그램을 선택 합니다 **시작** 메뉴를 선택한 후 **자세한** > **관리자 권한으로 실행** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="f01fa-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="f01fa-119">만들기는 **WCF 서비스 라이브러리** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="f01fa-120">**파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="f01fa-121">에 **새 프로젝트** 대화 상자의 왼쪽에서 확장 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **WCF** 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="f01fa-122">Visual Studio 창의 가운데에 프로젝트 템플릿 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="f01fa-123">선택 **WCF 서비스 라이브러리**합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="f01fa-124">표시 되지 않는 경우는 **WCF** 프로젝트 템플릿 범주를 설치 해야 할 수 있습니다 합니다 **Windows Communication Foundation** Visual Studio의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="f01fa-125">에 **새 프로젝트** 대화 상자에서를 **Visual Studio 설치 관리자 열기** 왼쪽에 링크 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="f01fa-126">선택 합니다 **개별 구성 요소** 탭 한 다음 찾아서 선택 **Windows Communication Foundation** 아래 합니다 **개발 작업** 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="f01fa-127">선택할 **수정** 구성 요소 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="f01fa-128">창의 아래쪽 섹션에서 입력 *GettingStartedLib* 에 대 한 합니다 **이름** 및 *GettingStarted* 에 대 한 합니다 **솔루션 이름**합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="f01fa-129">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-129">Select **OK**.</span></span>

      <span data-ttu-id="f01fa-130">Visual Studio에 세 개의 파일이 있는 프로젝트를 만듭니다. *IService1.cs* (또는 *IService1.vb* Visual Basic 프로젝트에 대 한), *Service1.cs* (또는 *Service1.vb* Visual Basic 프로젝트에 대 한), 및  *App.config*합니다. Visual Studio는 이러한 파일을 다음과 같이 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="f01fa-131">합니다 *IService1* 파일 서비스 계약의 기본 정의 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="f01fa-132">합니다 *Service1* 파일에는 서비스 계약의 기본 구현이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="f01fa-133">합니다 *App.config* 파일 Visual Studio WCF 서비스 호스트 도구를 사용 하 여 기본 서비스를 로드 하는 데 필요한 구성 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="f01fa-134">WCF 서비스 호스트 도구에 대 한 자세한 내용은 참조 하세요. [WCF 서비스 호스트 (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="f01fa-135">Visual Basic 개발자 환경 설정을 사용 하 여 Visual Studio를 설치한 경우 솔루션을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="f01fa-136">이 경우 선택 **옵션** 에서 합니다 **도구** 메뉴에서 선택한 **프로젝트 및 솔루션** > **일반** 에서 합니다 **옵션** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="f01fa-137">선택 **솔루션 항상 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-137">Select **Always show solution**.</span></span> <span data-ttu-id="f01fa-138">또한 확인 **만들어질 때 새 프로젝트 저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="f01fa-139">**솔루션 탐색기**오픈 합니다 **IService1.cs** 또는 **IService1.vb** 파일과 해당 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="f01fa-140">이 계약은 온라인 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-140">This contract defines an online calculator.</span></span> <span data-ttu-id="f01fa-141">알림을 `ICalculator` 으로 표시 된 인터페이스를 <xref:System.ServiceModel.ServiceContractAttribute> 특성 (으로 간소화 된 `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="f01fa-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="f01fa-142">이 특성은 계약 이름을 명확히 구분 하는 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="f01fa-143">코드를 사용 하 여 각 계산기 작업을 표시 합니다 <xref:System.ServiceModel.OperationContractAttribute> 특성 (으로 간소화 된 `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="f01fa-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f01fa-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f01fa-144">Next steps</span></span>

<span data-ttu-id="f01fa-145">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="f01fa-146">WCF 서비스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="f01fa-147">서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-147">Define a service contract interface.</span></span>

<span data-ttu-id="f01fa-148">WCF 서비스 계약을 구현 하는 방법을 알아보려면 다음 자습서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f01fa-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f01fa-149">자습서: WCF 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="f01fa-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
