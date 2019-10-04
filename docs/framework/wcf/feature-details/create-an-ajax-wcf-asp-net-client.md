---
title: Visual Studio에서 AJAX 사용 WCF 서비스 및 ASP.NET 클라이언트 만들기
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: a6d6e87de6200a5cb9bba566d595066673cdf9cf
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834783"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="873ad-102">방법: 서비스에 액세스 하는 AJAX 사용 WCF 서비스 및 ASP.NET 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="873ad-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="873ad-103">이 항목에서는 Visual Studio를 사용 하 여 AJAX 사용 Windows Communication Foundation (WCF) 서비스 및 서비스에 액세스 하는 ASP.NET 클라이언트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="873ad-104">ASP.NET 웹앱 만들기</span><span class="sxs-lookup"><span data-stu-id="873ad-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="873ad-105">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="873ad-106">**파일** 메뉴에서 **새** > **프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="873ad-107">**새 프로젝트** 대화 상자에서 **설치 된** >   > **비주얼 C#**  **웹** 범주를 확장 한 다음 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="873ad-108">프로젝트 이름을 **SandwichServices** 로 확인 하 고 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="873ad-109">**새 ASP.NET 웹 응용 프로그램** 대화 상자에서 **비어 있음** 을 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Visual Studio의 ASP.NET 웹 앱 형식 대화 상자](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="873ad-111">웹 폼 추가</span><span class="sxs-lookup"><span data-stu-id="873ad-111">Add a web form</span></span>

1. <span data-ttu-id="873ad-112">**솔루션 탐색기** 에서 SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 하 고**새 항목** **추가** > 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="873ad-113">**새 항목 추가** 대화 상자에서  >  **설치 된** > **비주얼 C#**  **웹** 범주를 확장 한 다음 **Web Form** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="873ad-114">기본 이름 (**WebForm1**)을 적용 한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="873ad-115">*WebForm1* 이 **소스** 뷰에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="873ad-116">본문 > 태그 안에  **\<** 다음 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="873ad-117">AJAX 사용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="873ad-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="873ad-118">**솔루션 탐색기** 에서 SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 하 고**새 항목** **추가** > 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="873ad-119">**새 항목 추가** 대화 상자  > 에서 **설치 된** > **비주얼 C#**  **웹** 범주를 확장 한 다음 **WCF 서비스 (AJAX 사용)** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Visual Studio의 WCF 서비스 (AJAX 사용) 항목 템플릿](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="873ad-121">서비스 이름을 **CostService** 로 지정한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="873ad-122">*CostService.svc.cs* 이 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="873ad-123">서비스에서 작업을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-123">Implement the operation in the service.</span></span> <span data-ttu-id="873ad-124">CostService 클래스에 다음 메서드를 추가 하 여 sandwiches 수량을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="873ad-125">서비스에 액세스 하도록 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="873ad-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="873ad-126">*WebForm1.aspx* 파일을 열어 **디자인** 보기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="873ad-127">**뷰** 메뉴에서 **도구 상자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="873ad-128">**AJAX 확장** 노드를 확장하여 **ScriptManager**를 폼에 드래그 앤 드롭하십시오.</span><span class="sxs-lookup"><span data-stu-id="873ad-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="873ad-129">**소스** 보기로 돌아가, **\<ScriptManager >** 태그 사이에 다음 코드를 추가하여 WCF 서비스의 경로를 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="873ad-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="873ad-130">Javascript 함수 `Calculate()`에 대 한 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="873ad-131">웹 폼의 **헤드** 섹션에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-131">Place the following code in the **head** section of the web form:</span></span>

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

   <span data-ttu-id="873ad-132">이 코드는 CostService의 메서드를 호출 하 여 세 sandwiches의 가격을 계산 하 고 **additionResult**이라는 범위에 결과를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="873ad-133">프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="873ad-133">Run the program</span></span>

<span data-ttu-id="873ad-134">*WebForm1* 에 포커스가 있는지 확인 한 다음 **시작** 단추를 눌러 웹 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="873ad-135">단추에는 녹색 삼각형이 표시 되 고 **IIS Express (Microsoft Edge)** 와 같은 내용이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="873ad-136">또는 <kbd>f5</kbd>키를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-136">Or, you can press <kbd>F5</kbd>.</span></span> <span data-ttu-id="873ad-137">**Price of 3 sandwiches** 단추를 클릭 하 여 "3.75"의 예상 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example"></a><span data-ttu-id="873ad-138">예제</span><span class="sxs-lookup"><span data-stu-id="873ad-138">Example</span></span>

<span data-ttu-id="873ad-139">*CostService.svc.cs* 파일의 전체 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-139">The following is the full code in the *CostService.svc.cs* file:</span></span>

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

<span data-ttu-id="873ad-140">다음은 *WebForm1 .aspx* 페이지의 전체 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="873ad-140">The following is the full contents of the *WebForm1.aspx* page:</span></span>

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
