---
title: AJAX 사용 WCF 서비스를 만들고 Visual Studio에서 ASP.NET 클라이언트
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 06fa3a9d0151f3b4b865c421f9960854ef471377
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807882"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>방법: 서비스에 액세스 하는 AJAX 사용 WCF 서비스와 ASP.NET 클라이언트 만들기

이 항목에서는 Visual Studio AJAX 지원 Windows Communication Foundation (WCF) 서비스를 만들고 서비스에 액세스 하는 ASP.NET 클라이언트를 사용 하는 방법을 보여 줍니다.

## <a name="create-an-aspnet-web-app"></a>ASP.NET 웹앱 만들기

1. Visual Studio를 엽니다.

1. **파일** 메뉴에서 **새로 만들기** > **프로젝트**

1. 에 **새 프로젝트** 대화 상자에서 확장을 **설치 됨** > **Visual C#** > **웹** 범주를 차례로 선택 **ASP.NET 웹 응용 프로그램 (.NET Framework)** 합니다.

1. 프로젝트 이름을 **SandwichServices** 누릅니다 **확인**합니다.

1. 에 **새 ASP.NET 웹 응용 프로그램** 대화 상자에서 **빈** 선택한 후 **확인**합니다.

   ![Visual Studio에서 ASP.NET 웹 앱 형식 대화](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Web form 추가

1. SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** > **새 항목**합니다.

1. 에 **새 항목 추가** 대화 상자에서 확장을 **설치 됨** > **Visual C#** > **웹** 범주를 차례로 선택 된 **Web Form** 템플릿.

1. 기본 이름 (**WebForm1**)를 선택한 후 **추가**합니다.

   *WebForm1.aspx* 열립니다 **소스** 보기.

1. 내에서 다음 태그를 추가 합니다  **\<본문 >** 태그:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>AJAX 사용 WCF 서비스 만들기

1. SandwichServices 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가** > **새 항목**합니다.

1. 에 **새 항목 추가** 대화 상자에서 확장을 **설치 됨** > **Visual C#** > **웹** 범주를 차례로 선택 된 **WCF 서비스 (AJAX 지원)** 템플릿.

   ![Visual Studio에서 WCF 서비스 (AJAX 지원) 항목 템플릿](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. 서비스의 이름을 **CostService** 선택한 후 **추가**합니다.

   *CostService.svc.cs* 편집기에서 열립니다.

1. 서비스에서 작업을 구현 합니다. Sandwiches 수량의 비용을 계산 하려면 CostService 클래스에 다음 메서드를 추가 합니다.

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>서비스에 액세스 하는 클라이언트 구성

1. *WebForm1.aspx* 파일을 열어 **디자인** 보기를 선택합니다.

2. **뷰** 메뉴에서 **도구 상자**를 선택합니다.

3. **AJAX 확장** 노드를 확장하여 **ScriptManager**를 폼에 드래그 앤 드롭하십시오.

4. **소스** 보기로 돌아가, **\<ScriptManager >** 태그 사이에 다음 코드를 추가하여 WCF 서비스의 경로를 지정하십시오.

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. Javascript 함수에 대 한 코드를 추가 `Calculate()`합니다. 다음 코드를 추가 합니다 **head** web form의 섹션:

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

   이 코드 3 sandwiches에 대 한 가격을 계산 하는 CostService의 메서드를 호출 하 고 라는 범위의 결과 표시 한 다음 **additionResult**합니다.

## <a name="run-the-program"></a>프로그램 실행

했는지 *WebForm1.aspx* 포커스가 누릅니다 **시작** 웹 클라이언트를 시작 합니다. 단추가 녹색 삼각형 있고 같은 고객과 **IIS Express (Microsoft Edge)** 합니다. 또는 눌러도 **F5**합니다. 클릭 합니다 **3 sandwiches의 가격** 예상된 된 출력 "3.75"를 생성 하는 단추입니다.

## <a name="example-code"></a>예제 코드

다음은 전체 코드는 *CostService.svc.cs* 파일:

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

다음은의 전체 콘텐츠를 *WebForm1.aspx* 페이지:

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
