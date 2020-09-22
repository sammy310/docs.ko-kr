---
title: My.WebServices 개체
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 0b63b44c2cd9d55094fb83fed6c04e4de528a25c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867208"
---
# <a name="mywebservices-object"></a><span data-ttu-id="ae1ed-102">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="ae1ed-102">My.WebServices Object</span></span>

<span data-ttu-id="ae1ed-103">현재 프로젝트에서 참조 하는 각 XML Web services의 단일 인스턴스를 만들고 액세스 하기 위한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-103">Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae1ed-104">설명</span><span class="sxs-lookup"><span data-stu-id="ae1ed-104">Remarks</span></span>  

 <span data-ttu-id="ae1ed-105">`My.WebServices` 개체는 현재 프로젝트에서 참조하는 각 웹 서비스의 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-105">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="ae1ed-106">필요에 따라 각 인스턴스가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-106">Each instance is instantiated on demand.</span></span> <span data-ttu-id="ae1ed-107">`My.WebServices` 개체의 속성을 통해 이러한 웹 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-107">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="ae1ed-108">속성 이름은 속성이 액세스하는 웹 서비스의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-108">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="ae1ed-109"><xref:System.Web.Services.Protocols.SoapHttpClientProtocol>에서 상속되는 모든 클래스는 웹 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-109">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span> <span data-ttu-id="ae1ed-110">프로젝트에 웹 서비스를 추가 하는 방법에 대 한 자세한 내용은 [응용 프로그램 웹 서비스 액세스](../../developing-apps/programming/accessing-application-web-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-110">For information about adding Web services to a project, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="ae1ed-111">`My.WebServices`개체는 현재 프로젝트와 연결 된 웹 서비스만 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-111">The `My.WebServices` object exposes only the Web services associated with the current project.</span></span> <span data-ttu-id="ae1ed-112">참조 된 Dll에 선언 된 웹 서비스에 대 한 액세스는 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-112">It does not provide access to Web services declared in referenced DLLs.</span></span> <span data-ttu-id="ae1ed-113">DLL이 제공 하는 웹 서비스에 액세스 하려면 웹 서비스의 정규화 된 이름을 *DllName*형식으로 사용 해야 합니다. *Webservicename*.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-113">To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*.</span></span> <span data-ttu-id="ae1ed-114">자세한 내용은 [응용 프로그램 웹 서비스 액세스](../../developing-apps/programming/accessing-application-web-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-114">For more information, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="ae1ed-115">개체와 해당 속성은 웹 응용 프로그램에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-115">The object and its properties are not available for Web applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ae1ed-116">속성</span><span class="sxs-lookup"><span data-stu-id="ae1ed-116">Properties</span></span>  

 <span data-ttu-id="ae1ed-117">개체의 각 속성은 `My.WebServices` 현재 프로젝트에서 참조 하는 웹 서비스의 인스턴스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-117">Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project.</span></span> <span data-ttu-id="ae1ed-118">속성의 이름은 속성이 액세스 하는 웹 서비스의 이름과 동일 하며, 속성 형식이 웹 서비스의 형식과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-118">The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae1ed-119">이름 충돌이 있는 경우 웹 서비스에 액세스 하기 위한 속성 이름은 *RootNamespace*_*Namespace* \_ *ServiceName*입니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-119">If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*.</span></span> <span data-ttu-id="ae1ed-120">예를 들어 라는 두 개의 웹 서비스를 가정 `Service1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-120">For example, consider two Web services named `Service1`.</span></span> <span data-ttu-id="ae1ed-121">이러한 서비스 중 하나가 루트 네임 스페이스 `WindowsApplication1` 및 네임 스페이스에 있는 경우를 `Namespace1` 사용 하 여 해당 서비스에 액세스 `My.WebServices.WindowsApplication1_Namespace1_Service1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-121">If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span></span>  
  
 <span data-ttu-id="ae1ed-122">개체의 속성 중 하나에 처음으로 액세스 하는 경우 `My.WebServices` 웹 서비스의 새 인스턴스를 만들어 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-122">When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it.</span></span> <span data-ttu-id="ae1ed-123">해당 속성에 대 한 후속 액세스는 웹 서비스의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-123">Subsequent accesses of that property return that instance of the Web service.</span></span>  
  
 <span data-ttu-id="ae1ed-124">웹 서비스의 속성에를 할당 하 여 웹 서비스를 삭제할 수 있습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="ae1ed-124">You can dispose of a Web service by assigning `Nothing` to the property for that Web service.</span></span> <span data-ttu-id="ae1ed-125">속성 setter는 `Nothing` 저장 된 값에을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-125">The property setter assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="ae1ed-126">속성에 이외의 값을 할당 하면 `Nothing` setter가 예외를 throw <xref:System.ArgumentException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="ae1ed-127">`My.WebServices`또는 연산자를 사용 하 여 개체의 속성이 웹 서비스의 인스턴스를 저장 하는지 여부를 테스트할 수 있습니다 `Is` `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="ae1ed-127">You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="ae1ed-128">이러한 연산자를 사용 하 여 속성 값이 인지 확인할 수 있습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="ae1ed-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae1ed-129">일반적으로 `Is` 또는 `IsNot` 연산자는 비교를 수행 하기 위해 속성의 값을 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="ae1ed-130">그러나 속성이 현재 저장 된 경우 `Nothing` 속성은 웹 서비스의 새 인스턴스를 만든 다음 해당 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-130">However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance.</span></span> <span data-ttu-id="ae1ed-131">그러나 Visual Basic 컴파일러는 개체의 속성을 특수 하 `My.WebServices` 게 처리 하 고 `Is` 또는 연산자가 `IsNot` 해당 값을 변경 하지 않고 속성의 상태를 확인할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-131">However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae1ed-132">예제</span><span class="sxs-lookup"><span data-stu-id="ae1ed-132">Example</span></span>  

 <span data-ttu-id="ae1ed-133">이 예제에서는 `FahrenheitToCelsius` XML Web services의 메서드를 호출 `TemperatureConverter` 하 고 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-133">This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.</span></span>  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 <span data-ttu-id="ae1ed-134">이 예제가 작동 하려면 프로젝트가 이라는 웹 서비스를 참조 해야 하 `Converter` 고 웹 서비스에서 메서드를 노출 해야 합니다 `ConvertTemperature` .</span><span class="sxs-lookup"><span data-stu-id="ae1ed-134">For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method.</span></span> <span data-ttu-id="ae1ed-135">자세한 내용은 [응용 프로그램 웹 서비스 액세스](../../developing-apps/programming/accessing-application-web-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-135">For more information, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="ae1ed-136">이 코드는 웹 응용 프로그램 프로젝트에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1ed-136">This code does not work in a Web application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae1ed-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae1ed-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="ae1ed-138">프로젝트 형식에 따라 가용성</span><span class="sxs-lookup"><span data-stu-id="ae1ed-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="ae1ed-139">프로젝트 형식</span><span class="sxs-lookup"><span data-stu-id="ae1ed-139">Project type</span></span>|<span data-ttu-id="ae1ed-140">사용 가능</span><span class="sxs-lookup"><span data-stu-id="ae1ed-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="ae1ed-141">Windows 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="ae1ed-141">Windows Application</span></span>|<span data-ttu-id="ae1ed-142">**예**</span><span class="sxs-lookup"><span data-stu-id="ae1ed-142">**Yes**</span></span>|  
|<span data-ttu-id="ae1ed-143">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ae1ed-143">Class Library</span></span>|<span data-ttu-id="ae1ed-144">**예**</span><span class="sxs-lookup"><span data-stu-id="ae1ed-144">**Yes**</span></span>|  
|<span data-ttu-id="ae1ed-145">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="ae1ed-145">Console Application</span></span>|<span data-ttu-id="ae1ed-146">**예**</span><span class="sxs-lookup"><span data-stu-id="ae1ed-146">**Yes**</span></span>|  
|<span data-ttu-id="ae1ed-147">Windows 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ae1ed-147">Windows Control Library</span></span>|<span data-ttu-id="ae1ed-148">**예**</span><span class="sxs-lookup"><span data-stu-id="ae1ed-148">**Yes**</span></span>|  
|<span data-ttu-id="ae1ed-149">웹 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ae1ed-149">Web Control Library</span></span>|<span data-ttu-id="ae1ed-150">**예**</span><span class="sxs-lookup"><span data-stu-id="ae1ed-150">**Yes**</span></span>|  
|<span data-ttu-id="ae1ed-151">Windows 서비스</span><span class="sxs-lookup"><span data-stu-id="ae1ed-151">Windows Service</span></span>|<span data-ttu-id="ae1ed-152">**예**</span><span class="sxs-lookup"><span data-stu-id="ae1ed-152">**Yes**</span></span>|  
|<span data-ttu-id="ae1ed-153">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="ae1ed-153">Web Site</span></span>|<span data-ttu-id="ae1ed-154">예</span><span class="sxs-lookup"><span data-stu-id="ae1ed-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae1ed-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae1ed-155">See also</span></span>

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [<span data-ttu-id="ae1ed-156">애플리케이션 웹 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="ae1ed-156">Accessing Application Web Services</span></span>](../../developing-apps/programming/accessing-application-web-services.md)
