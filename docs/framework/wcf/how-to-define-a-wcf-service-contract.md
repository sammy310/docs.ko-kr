---
title: '자습서: Windows Communication Foundation 서비스 계약 정의'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: ba88fc6ba4cba8d46ed1b43080d471b1b7c4bd75
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928882"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="98478-102">자습서: Windows Communication Foundation 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="98478-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="98478-103">이 자습서에서는 WCF (기본 Windows Communication Foundation) 응용 프로그램을 만드는 데 필요한 5 가지 작업 중 첫 번째 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="98478-104">자습서에 대 한 개요를 보려면 [자습서: Windows Communication Foundation 응용 프로그램](getting-started-tutorial.md)을 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="98478-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="98478-105">WCF 서비스를 만들 때 첫 번째 작업은 서비스 계약을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98478-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="98478-106">서비스 계약은 서비스가 지원하는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="98478-107">작업은 웹 서비스 메서드로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="98478-108">Visual C# 또는 VB (Visual Basic) 인터페이스를 정의 하 여 서비스 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98478-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="98478-109">인터페이스에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="98478-110">인터페이스의 각 메서드는 특정 서비스 작업에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="98478-111">각 인터페이스에 대해 <xref:System.ServiceModel.ServiceContractAttribute> 특성을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="98478-112">각 작업/메서드에 대해 <xref:System.ServiceModel.OperationContractAttribute> 특성을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="98478-113">이 자습서에서는 다음 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="98478-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="98478-114">**WCF 서비스 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98478-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="98478-115">서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="98478-116">WCF 서비스 라이브러리 프로젝트를 만들고 서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="98478-117">관리자 권한으로 Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98478-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="98478-118">이렇게 하려면 **시작** 메뉴에서 Visual Studio 프로그램 **을 선택 하** > 고 바로 가기 메뉴에서**관리자 권한으로 실행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="98478-119">**WCF 서비스 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98478-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="98478-120">**파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="98478-121">**새 프로젝트** 대화 상자의 왼쪽에서  **C# 비주얼** 또는 **Visual Basic**을 확장 한 다음 **WCF** 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="98478-122">Visual Studio는 창의 가운데 섹션에 프로젝트 템플릿 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="98478-123">**WCF 서비스 라이브러리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="98478-124">**WCF** 프로젝트 템플릿 범주가 표시 되지 않으면 Visual Studio의 **Windows Communication Foundation** 구성 요소를 설치 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="98478-125">**새 프로젝트** 대화 상자에서 왼쪽에 있는 **Visual Studio 설치 관리자 열기** 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="98478-126">**개별 구성 요소** 탭을 선택한 다음 **개발 활동** 범주 아래에서 **Windows Communication Foundation** 을 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="98478-127">**수정** 을 선택 하 여 구성 요소 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="98478-128">창의 아래쪽 섹션에서 **솔루션 이름**에 대해 시작 된 **이름** 및 *getGettingStartedLib* 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="98478-129">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-129">Select **OK**.</span></span>

      <span data-ttu-id="98478-130">Visual Studio는 세 개의 파일이 있는 프로젝트를 만듭니다. *IService1.cs* (또는 Visual Basic 프로젝트의 경우 *IService1* , *Service1.cs* (또는 Visual Basic 프로젝트의 경우 *Service1 .vb* ) 및 *app.config*. Visual Studio는 다음과 같은 파일을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="98478-131">*IService1* 파일에는 서비스 계약의 기본 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="98478-132">*Service1* 파일에는 서비스 계약의 기본 구현이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="98478-133">*App.config* 파일에는 VISUAL Studio WCF 서비스 호스트 도구를 사용 하 여 기본 서비스를 로드 하는 데 필요한 구성 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="98478-134">WCF 서비스 호스트 도구에 대 한 자세한 내용은 [Wcf 서비스 호스트 (wcfsvchost.exe)](wcf-service-host-wcfsvchost-exe.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="98478-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="98478-135">Visual Basic 개발자 환경 설정을 사용 하 여 Visual Studio를 설치한 경우 솔루션이 숨겨질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="98478-136">이 경우 **도구** 메뉴에서 **옵션** 을 선택한 다음 **옵션** 창에서 **프로젝트 및 솔루션** > **일반** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="98478-137">**솔루션 항상 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-137">Select **Always show solution**.</span></span> <span data-ttu-id="98478-138">또한 **만들어질 때 새 프로젝트 저장** 이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="98478-139">**솔루션 탐색기**에서 **IService1.cs** 또는 **IService1** 파일을 열고 해당 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="98478-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="98478-140">이 계약은 온라인 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-140">This contract defines an online calculator.</span></span> <span data-ttu-id="98478-141">인터페이스는 `ICalculator` <xref:System.ServiceModel.ServiceContractAttribute> 특성으로 표시 됩니다 (단순화 `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="98478-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="98478-142">이 특성은 계약 이름을 명확 하 게 구분 하는 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="98478-143">이 코드는 각 계산기 작업을 <xref:System.ServiceModel.OperationContractAttribute> 특성 (로 `OperationContract`간소화)으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="98478-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="98478-144">Next steps</span></span>

<span data-ttu-id="98478-145">이 자습서에서는 다음 작업을 수행하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="98478-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="98478-146">WCF 서비스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98478-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="98478-147">서비스 계약 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-147">Define a service contract interface.</span></span>

<span data-ttu-id="98478-148">WCF 서비스 계약을 구현 하는 방법에 대해 알아보려면 다음 자습서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="98478-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="98478-149">자습서: WCF 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="98478-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
