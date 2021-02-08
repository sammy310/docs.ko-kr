---
description: '자세한 정보: 방법: 서비스에 액세스 하는 AJAX-Enabled WCF 서비스 및 ASP.NET 클라이언트 만들기'
title: Visual Studio에서 AJAX-Enabled WCF 서비스 및 ASP.NET 클라이언트 만들기
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 59b0cab9b28dd68b27529b5d880138cc283144a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780351"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="d0466-103">방법: AJAX 사용 WCF 서비스 및 해당 서비스에 액세스하는 ASP.NET 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="d0466-103">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="d0466-104">이 항목에서는 Visual Studio를 사용 하 여 AJAX 사용 Windows Communication Foundation (WCF) 서비스 및 서비스에 액세스 하는 ASP.NET 클라이언트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-104">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="d0466-105">ASP.NET 웹앱 만들기</span><span class="sxs-lookup"><span data-stu-id="d0466-105">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="d0466-106">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-106">Open Visual Studio.</span></span>

1. <span data-ttu-id="d0466-107">**파일** 메뉴에서 **새**  >  **프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-107">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="d0466-108">**새 프로젝트** 대화 상자에서 **설치 된**  >  **Visual c #**  >  **웹** 범주를 확장 한 다음 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-108">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="d0466-109">프로젝트 이름을 **SandwichServices** 로 확인 하 고 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-109">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="d0466-110">**새 ASP.NET 웹 응용 프로그램** 대화 상자에서 **비어 있음** 을 선택 하 고 **확인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-110">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Visual Studio의 ASP.NET 웹 앱 형식 대화 상자](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="d0466-112">웹 폼 추가</span><span class="sxs-lookup"><span data-stu-id="d0466-112">Add a web form</span></span>

1. <span data-ttu-id="d0466-113">**솔루션 탐색기** 에서 SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 하 고  >  **새 항목** 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-113">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d0466-114">**새 항목 추가** 대화 상자에서 **설치 된**  >  **Visual c #**  >  **웹** 범주를 확장 한 다음 **web Form** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-114">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="d0466-115">기본 이름 (**WebForm1**)을 적용 한 다음 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-115">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="d0466-116">*WebForm1* 이 **소스** 뷰에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-116">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="d0466-117">태그 내에 다음 태그를 추가 합니다 **\<body>** .</span><span class="sxs-lookup"><span data-stu-id="d0466-117">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="d0466-118">AJAX 사용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="d0466-118">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="d0466-119">**솔루션 탐색기** 에서 SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 하 고  >  **새 항목** 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-119">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d0466-120">**새 항목 추가** 대화 상자에서 **설치 된**  >  **Visual c #**  >  **웹** 범주를 확장 한 다음 **WCF 서비스 (AJAX 사용)** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-120">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Visual Studio의 WCF 서비스 (AJAX 사용) 항목 템플릿](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="d0466-122">서비스 이름을 **CostService** 로 지정한 다음 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-122">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="d0466-123">*CostService.svc.cs* 이 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-123">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="d0466-124">서비스에서 작업을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-124">Implement the operation in the service.</span></span> <span data-ttu-id="d0466-125">CostService 클래스에 다음 메서드를 추가 하 여 sandwiches 수량을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-125">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="d0466-126">서비스에 액세스 하도록 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d0466-126">Configure the client to access the service</span></span>

1. <span data-ttu-id="d0466-127">*WebForm1 .aspx* 파일을 열고 **디자인** 뷰를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-127">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="d0466-128">**보기** 메뉴에서 **도구 상자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-128">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="d0466-129">**AJAX 확장** 노드를 확장 하 고 **ScriptManager** 를 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-129">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="d0466-130">**원본** 뷰로 돌아가서 태그 사이에 다음 코드를 추가 하 여 **\<ScriptManager>** WCF 서비스에 대 한 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-130">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="d0466-131">JavaScript 함수에 대 한 코드를 추가 `Calculate()` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-131">Add the code for the JavaScript function `Calculate()`.</span></span> <span data-ttu-id="d0466-132">웹 폼의 **헤드** 섹션에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-132">Place the following code in the **head** section of the web form:</span></span>

    ```html
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   <span data-ttu-id="d0466-133">이 코드는 CostService의 메서드를 호출 하 여 세 sandwiches의 가격을 계산 하 고 **additionResult** 이라는 범위에 결과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-133">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="d0466-134">프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="d0466-134">Run the program</span></span>

<span data-ttu-id="d0466-135">*WebForm1* 에 포커스가 있는지 확인 한 다음 **시작** 단추를 눌러 웹 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-135">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="d0466-136">단추에는 녹색 삼각형이 표시 되 고 **IIS Express (Microsoft Edge)** 와 같은 내용이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-136">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="d0466-137">또는 <kbd>f5</kbd>키를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-137">Or, you can press <kbd>F5</kbd>.</span></span> <span data-ttu-id="d0466-138">**Price of 3 sandwiches** 단추를 클릭 하 여 "3.75"의 예상 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-138">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example"></a><span data-ttu-id="d0466-139">예제</span><span class="sxs-lookup"><span data-stu-id="d0466-139">Example</span></span>

<span data-ttu-id="d0466-140">*CostService.svc.cs* 파일의 전체 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-140">The following is the full code in the *CostService.svc.cs* file:</span></span>

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

<span data-ttu-id="d0466-141">다음은 *WebForm1 .aspx* 페이지의 전체 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="d0466-141">The following is the full contents of the *WebForm1.aspx* page:</span></span>

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```
