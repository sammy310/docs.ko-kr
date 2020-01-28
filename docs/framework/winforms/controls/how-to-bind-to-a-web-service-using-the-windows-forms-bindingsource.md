---
title: BindingSource를 사용 하 여 웹 서비스에 바인딩
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
ms.openlocfilehash: 0680c73e578577cf40158761f6c635fe30ff9f4d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746677"
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="cba61-102">방법: Windows Forms BindingSource를 사용하여 웹 서비스에 바인딩</span><span class="sxs-lookup"><span data-stu-id="cba61-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="cba61-103">XML Web services 호출에서 얻은 결과에 Windows Form 컨트롤을 바인딩하려면 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="cba61-104">이 절차는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 형식에 바인딩하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="cba61-105">웹 서비스에 의해 노출되는 메서드와 형식이 포함된 클라이언트 측 프록시를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="cba61-106">웹 서비스(.asmx) 자체 또는 WSDL(Web Services Description Language) 파일에서 클라이언트 측 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="cba61-107">또한 클라이언트 측 프록시는 웹 서비스에서 공용 속성으로 사용되는 복합 형식의 필드를 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="cba61-108">그리고 나서 <xref:System.Windows.Forms.BindingSource>를 웹 서비스 프록시에 노출된 형식의 하나에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="cba61-109">클라이언트 측 프록시를 만들고 바인딩하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-109">To create and bind to a client-side proxy</span></span>  
  
1. <span data-ttu-id="cba61-110">적절한 네임스페이스를 사용하여 선택한 디렉터리에서 Windows Form을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2. <span data-ttu-id="cba61-111">폼에 <xref:System.Windows.Forms.BindingSource> 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3. <span data-ttu-id="cba61-112">Windows SDK (소프트웨어 개발 키트) 명령 프롬프트를 열고 양식이 있는 동일한 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-112">Open the Windows Software Development Kit (SDK) command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4. <span data-ttu-id="cba61-113">WSDL 도구를 사용하여 `wsdl`, 웹 서비스에 대한 .asmx 또는 WSDL 파일의 URL, 애플리케이션의 네임스페이스를 차례로 입력하고 선택적으로 사용 중인 언어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="cba61-114">다음 코드 예제에서는 `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`에 있는 웹 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-114">The following code example uses the Web service located at `http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx`.</span></span> <span data-ttu-id="cba61-115">예를 들어 C# 유형 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService` 또는 Visual Basic 유형 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="cba61-116">WSDL 도구에 경로를 인수로 전달하면 지정된 언어로 애플리케이션과 같은 디렉터리 및 네임스페이스에 클라이언트 측 프록시가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="cba61-117">Visual Studio를 사용 하는 경우 프로젝트에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-117">If you are using Visual Studio, add the file to your project.</span></span>  
  
5. <span data-ttu-id="cba61-118">바인딩할 클라이언트 측 프록시의 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="cba61-119">이는 일반적으로 웹 서비스에서 제공된 메서드가 반환한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="cba61-120">선택된 형식의 필드는 바인딩용 공용 속성으로 노출되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6. <span data-ttu-id="cba61-121"><xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성을 웹 서비스 클라이언트 측 프록시에 포함된 원하는 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="cba61-122">웹 서비스에 바인딩된 BindingSource에 컨트롤을 바인딩하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
- <span data-ttu-id="cba61-123">컨트롤을 <xref:System.Windows.Forms.BindingSource>에 바인딩하여 원하는 웹 서비스 형식의 공용 속성을 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="cba61-124">예</span><span class="sxs-lookup"><span data-stu-id="cba61-124">Example</span></span>  
 <span data-ttu-id="cba61-125">다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 웹 서비스에 바인딩하는 방법과 텍스트 상자를 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩하는 방법을 차례로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="cba61-126">단추를 클릭할 때 웹 서비스 메서드가 호출되고 결과가 `textbox1`에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cba61-127">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cba61-127">Compiling the Code</span></span>  
 <span data-ttu-id="cba61-128">이 전체 예제에는 `Main` 메서드와 클라이언트 측 프록시 코드의 간략 버전이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="cba61-129">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cba61-129">This example requires:</span></span>  
  
- <span data-ttu-id="cba61-130">System, System.Drawing, System.Web.Services, System.Windows.Forms 및 System.Xml 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="cba61-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba61-131">참조</span><span class="sxs-lookup"><span data-stu-id="cba61-131">See also</span></span>

- [<span data-ttu-id="cba61-132">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cba61-132">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="cba61-133">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="cba61-133">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
