---
title: AJAX 사용 WCF 서비스를 만들고 Visual Studio에서 ASP.NET 클라이언트
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 06fa3a9d0151f3b4b865c421f9960854ef471377
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754611"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="49e8e-102">방법: 서비스에 액세스 하는 AJAX 사용 WCF 서비스와 ASP.NET 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="49e8e-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="49e8e-103">이 항목에서는 Visual Studio AJAX 지원 Windows Communication Foundation (WCF) 서비스를 만들고 서비스에 액세스 하는 ASP.NET 클라이언트를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="49e8e-104">ASP.NET 웹앱 만들기</span><span class="sxs-lookup"><span data-stu-id="49e8e-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="49e8e-105">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="49e8e-106">**파일** 메뉴에서 **새로 만들기** > **프로젝트**</span><span class="sxs-lookup"><span data-stu-id="49e8e-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="49e8e-107">에 **새 프로젝트** 대화 상자에서 확장을 **설치 됨** > **Visual C#** > **웹** 범주를 차례로 선택 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="49e8e-108">프로젝트 이름을 **SandwichServices** 누릅니다 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="49e8e-109">에 **새 ASP.NET 웹 응용 프로그램** 대화 상자에서 **빈** 선택한 후 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Visual Studio에서 ASP.NET 웹 앱 형식 대화](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="49e8e-111">Web form 추가</span><span class="sxs-lookup"><span data-stu-id="49e8e-111">Add a web form</span></span>

1. <span data-ttu-id="49e8e-112">SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** > **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="49e8e-113">에 **새 항목 추가** 대화 상자에서 확장을 **설치 됨** > **Visual C#** > **웹** 범주를 차례로 선택 된 **Web Form** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="49e8e-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="49e8e-114">기본 이름 (**WebForm1**)를 선택한 후 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="49e8e-115">*WebForm1.aspx* 열립니다 **소스** 보기.</span><span class="sxs-lookup"><span data-stu-id="49e8e-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="49e8e-116">내에서 다음 태그를 추가 합니다  **\<본문 >** 태그:</span><span class="sxs-lookup"><span data-stu-id="49e8e-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="49e8e-117">AJAX 사용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="49e8e-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="49e8e-118">SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** > **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="49e8e-119">에 **새 항목 추가** 대화 상자에서 확장을 **설치 됨** > **Visual C#** > **웹** 범주를 차례로 선택 된 **WCF 서비스 (AJAX 지원)** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="49e8e-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Visual Studio에서 WCF 서비스 (AJAX 지원) 항목 템플릿](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="49e8e-121">서비스의 이름을 **CostService** 선택한 후 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="49e8e-122">*CostService.svc.cs* 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="49e8e-123">서비스에서 작업을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-123">Implement the operation in the service.</span></span> <span data-ttu-id="49e8e-124">Sandwiches 수량의 비용을 계산 하려면 CostService 클래스에 다음 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="49e8e-125">서비스에 액세스 하는 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="49e8e-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="49e8e-126">*WebForm1.aspx* 파일을 열어 **디자인** 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="49e8e-127">**뷰** 메뉴에서 **도구 상자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="49e8e-128">**AJAX 확장** 노드를 확장하여 **ScriptManager**를 폼에 드래그 앤 드롭하십시오.</span><span class="sxs-lookup"><span data-stu-id="49e8e-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="49e8e-129">**소스** 보기로 돌아가, **\<ScriptManager >** 태그 사이에 다음 코드를 추가하여 WCF 서비스의 경로를 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="49e8e-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="49e8e-130">Javascript 함수에 대 한 코드를 추가 `Calculate()`합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="49e8e-131">다음 코드를 추가 합니다 **head** web form의 섹션:</span><span class="sxs-lookup"><span data-stu-id="49e8e-131">Place the following code in the **head** section of the web form:</span></span>

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

   <span data-ttu-id="49e8e-132">이 코드 3 sandwiches에 대 한 가격을 계산 하는 CostService의 메서드를 호출 하 고 라는 범위의 결과 표시 한 다음 **additionResult**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="49e8e-133">프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="49e8e-133">Run the program</span></span>

<span data-ttu-id="49e8e-134">했는지 *WebForm1.aspx* 포커스가 누릅니다 **시작** 웹 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="49e8e-135">단추가 녹색 삼각형 있고 같은 고객과 **IIS Express (Microsoft Edge)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="49e8e-136">또는 눌러도 **F5**합니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-136">Or, you can press **F5**.</span></span> <span data-ttu-id="49e8e-137">클릭 합니다 **3 sandwiches의 가격** 예상된 된 출력 "3.75"를 생성 하는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="49e8e-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="49e8e-138">예제 코드</span><span class="sxs-lookup"><span data-stu-id="49e8e-138">Example code</span></span>

<span data-ttu-id="49e8e-139">다음은 전체 코드는 *CostService.svc.cs* 파일:</span><span class="sxs-lookup"><span data-stu-id="49e8e-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

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

<span data-ttu-id="49e8e-140">다음은의 전체 콘텐츠를 *WebForm1.aspx* 페이지:</span><span class="sxs-lookup"><span data-stu-id="49e8e-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

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
