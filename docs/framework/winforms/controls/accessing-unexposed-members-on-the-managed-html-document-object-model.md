---
title: 관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988398"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="b6d75-102">관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="b6d75-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="b6d75-103">관리 되는 html 문서 개체 모델 (DOM)에는 모든 <xref:System.Windows.Forms.HtmlElement> HTML 요소가 공통적으로 포함 하는 속성, 메서드 및 이벤트를 노출 하는 이라는 클래스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="b6d75-104">그러나 경우에 따라 관리 되는 인터페이스가 직접 노출 하지 않는 멤버에 액세스 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="b6d75-105">이 항목에서는 웹 페이지 내부에 정의 된 JScript 및 VBScript 함수를 비롯 하 여 노출 되지 않은 멤버에 액세스 하는 두 가지 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-105">This topic examines two ways for accessing unexposed members, including JScript and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="b6d75-106">관리 되는 인터페이스를 통해 노출 되지 않은 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="b6d75-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="b6d75-107"><xref:System.Windows.Forms.HtmlDocument>및 <xref:System.Windows.Forms.HtmlElement> 는 노출 되지 않은 멤버에 액세스할 수 있도록 하는 네 가지 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="b6d75-108">다음 표에서는 형식 및 해당 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="b6d75-109">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="b6d75-109">Member Type</span></span>|<span data-ttu-id="b6d75-110">메서드</span><span class="sxs-lookup"><span data-stu-id="b6d75-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b6d75-111">속성 (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="b6d75-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="b6d75-112">메서드</span><span class="sxs-lookup"><span data-stu-id="b6d75-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="b6d75-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="b6d75-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="b6d75-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="b6d75-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="b6d75-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="b6d75-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="b6d75-116">이러한 메서드를 사용 하는 경우 올바른 기본 형식의 요소가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="b6d75-117">사용자가 서버에 전송 하기 전에 `Submit` `FORM`의 값에 대 `FORM` 한 사전 처리를 수행할 수 있도록 HTML 페이지에서 요소의 이벤트를 수신 대기 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="b6d75-118">HTML에 대 한 제어 권한이 있는 경우 고유한 `FORM` `ID` 특성을 갖도록을 정의 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```html  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="b6d75-119"><xref:System.Windows.Forms.WebBrowser> 컨트롤에이 페이지를 로드 한 후 메서드를 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 사용 하 여를 인수로 사용 하 `FORM` 여 `form1` 런타임에를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="b6d75-120">관리 되지 않는 인터페이스 액세스</span><span class="sxs-lookup"><span data-stu-id="b6d75-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="b6d75-121">각 DOM 클래스에서 노출 하는 관리 되지 않는 COM (구성 요소 개체 모델) 인터페이스를 사용 하 여 관리 되는 HTML DOM에서 노출 되지 않은 멤버에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="b6d75-122">노출 되지 않은 멤버에 대 한 여러 호출을 수행 해야 하는 경우 또는 노출 되지 않은 멤버가 관리 되는 HTML DOM에서 래핑된 다른 관리 되지 않는 인터페이스를 반환 하는 경우에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="b6d75-123">다음 표에서는 관리 되는 HTML DOM을 통해 노출 되는 관리 되지 않는 인터페이스를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="b6d75-124">각 링크를 클릭 하 여 사용법 및 예제 코드에 대 한 설명을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="b6d75-125">형식</span><span class="sxs-lookup"><span data-stu-id="b6d75-125">Type</span></span>|<span data-ttu-id="b6d75-126">관리 되지 않는 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6d75-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="b6d75-127">COM 인터페이스를 사용 하는 가장 쉬운 방법은 지원 되지 않지만 응용 프로그램에서 관리 되지 않는 HTML DOM 라이브러리 (MSHTML)에 대 한 참조를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="b6d75-128">자세한 내용은 [기술 자료 문서 934368](https://support.microsoft.com/kb/934368)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6d75-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="b6d75-129">스크립트 함수 액세스</span><span class="sxs-lookup"><span data-stu-id="b6d75-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="b6d75-130">HTML 페이지는 JScript 또는 VBScript와 같은 스크립팅 언어를 사용 하 여 하나 이상의 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-130">An HTML page can define one or more functions by using a scripting language such as JScript or VBScript.</span></span> <span data-ttu-id="b6d75-131">이러한 함수는 페이지의 `SCRIPT` 페이지 내에 배치 되 고 요청 시 또는 DOM의 이벤트에 대 한 응답으로 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="b6d75-132">메서드를 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 사용 하 여 HTML 페이지에서 정의 하는 모든 스크립트 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="b6d75-133">스크립트 메서드가 HTML 요소를 반환 하는 경우 캐스트를 사용 하 여이 반환 결과 <xref:System.Windows.Forms.HtmlElement>를로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6d75-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="b6d75-134">자세한 내용과 예제 코드는를 참조 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>하세요.</span><span class="sxs-lookup"><span data-stu-id="b6d75-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d75-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6d75-135">See also</span></span>

- [<span data-ttu-id="b6d75-136">관리되는 HTML 문서 개체 모델 사용</span><span class="sxs-lookup"><span data-stu-id="b6d75-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
