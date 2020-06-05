---
title: My.Resources 개체
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 2b7c82c31d2e31ccbf573cf1dfa138af2d99ce29
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372463"
---
# <a name="myresources-object"></a><span data-ttu-id="8d5c1-102">My.Resources 개체</span><span class="sxs-lookup"><span data-stu-id="8d5c1-102">My.Resources Object</span></span>
<span data-ttu-id="8d5c1-103">응용 프로그램의 리소스에 액세스 하기 위한 속성 및 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d5c1-104">설명</span><span class="sxs-lookup"><span data-stu-id="8d5c1-104">Remarks</span></span>  
 <span data-ttu-id="8d5c1-105">`My.Resources`개체는 응용 프로그램의 리소스에 대 한 액세스를 제공 하 고 응용 프로그램에 대 한 리소스를 동적으로 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="8d5c1-106">자세한 내용은 [응용 프로그램 리소스 관리 (.net)](/visualstudio/ide/managing-application-resources-dotnet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-106">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="8d5c1-107">`My.Resources` 개체는 글로벌 리소스만 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="8d5c1-108">양식과 관련된 리소스 파일에 대한 액세스 권한은 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="8d5c1-109">양식에서 양식 리소스에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-109">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="8d5c1-110">개체에서 응용 프로그램의 문화권 관련 리소스 파일에 액세스할 수 있습니다 `My.Resources` .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-110">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="8d5c1-111">기본적으로 개체는 `My.Resources` 속성의 문화권과 일치 하는 리소스 파일에서 리소스를 조회 합니다 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-111">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="8d5c1-112">그러나이 동작을 재정의 하 고 리소스에 사용할 특정 문화권을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-112">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="8d5c1-113">자세한 내용은 [데스크톱 앱의 리소스](../../../framework/resources/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-113">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8d5c1-114">속성</span><span class="sxs-lookup"><span data-stu-id="8d5c1-114">Properties</span></span>  
 <span data-ttu-id="8d5c1-115">개체의 속성은 `My.Resources` 응용 프로그램의 리소스에 대 한 읽기 전용 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-115">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="8d5c1-116">리소스를 추가 하거나 제거 하려면 **프로젝트 디자이너**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-116">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="8d5c1-117">Context.resourcename을 사용 하 여 **프로젝트 디자이너** 를 통해 추가 된 리소스에 액세스할 수 있습니다 `My.Resources.` *resourceName*.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-117">You can access resources added through the **Project Designer** by using `My.Resources.`*resourceName*.</span></span>  
  
 <span data-ttu-id="8d5c1-118">**솔루션 탐색기** 에서 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **새 항목 추가** 또는 **기존 항목 추가** 를 클릭 하 여 리소스 파일을 추가 하거나 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-118">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="8d5c1-119">`My.Resources.` *ResourceFileName* `.` *context.resourcename*을 사용 하 여 이러한 방식으로 추가 된 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-119">You can access resources added in this manner by using `My.Resources.`*resourceFileName*`.`*resourceName*.</span></span>  
  
 <span data-ttu-id="8d5c1-120">각 리소스에는 이름, 범주 및 값이 있으며, 이러한 리소스 설정에 따라 리소스에 액세스 하는 속성이 개체에 표시 되는 방식이 결정 됩니다 `My.Resources` .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-120">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="8d5c1-121">**프로젝트 디자이너**에 추가 된 리소스:</span><span class="sxs-lookup"><span data-stu-id="8d5c1-121">For resources added in the **Project Designer**:</span></span>  
  
- <span data-ttu-id="8d5c1-122">이름은 속성의 이름을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-122">The name determines the name of the property,</span></span>  
  
- <span data-ttu-id="8d5c1-123">리소스 데이터는 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-123">The resource data is the value of the property,</span></span>  
  
- <span data-ttu-id="8d5c1-124">범주는 속성의 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-124">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="8d5c1-125">Category</span><span class="sxs-lookup"><span data-stu-id="8d5c1-125">Category</span></span>|<span data-ttu-id="8d5c1-126">속성 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8d5c1-126">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="8d5c1-127">**문자열**</span><span class="sxs-lookup"><span data-stu-id="8d5c1-127">**Strings**</span></span>|[<span data-ttu-id="8d5c1-128">String</span><span class="sxs-lookup"><span data-stu-id="8d5c1-128">String</span></span>](../data-types/string-data-type.md)|  
|<span data-ttu-id="8d5c1-129">**이미지**</span><span class="sxs-lookup"><span data-stu-id="8d5c1-129">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="8d5c1-130">**아이콘**</span><span class="sxs-lookup"><span data-stu-id="8d5c1-130">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="8d5c1-131">**비디오**</span><span class="sxs-lookup"><span data-stu-id="8d5c1-131">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="8d5c1-132"><xref:System.IO.UnmanagedMemoryStream>클래스는 클래스에서 파생 <xref:System.IO.Stream> 되므로 메서드 등의 스트림을 사용 하는 메서드와 함께 사용할 수 있습니다 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-132">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="8d5c1-133">**파일**</span><span class="sxs-lookup"><span data-stu-id="8d5c1-133">**Files**</span></span>|<span data-ttu-id="8d5c1-134">-   텍스트 파일의 [문자열](../data-types/string-data-type.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-134">-   [String](../data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="8d5c1-135">-   <xref:System.Drawing.Bitmap>이미지 파일의 경우</span><span class="sxs-lookup"><span data-stu-id="8d5c1-135">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="8d5c1-136">-   <xref:System.Drawing.Icon>아이콘 파일의 경우</span><span class="sxs-lookup"><span data-stu-id="8d5c1-136">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="8d5c1-137">-   <xref:System.IO.UnmanagedMemoryStream>사운드 파일의 경우</span><span class="sxs-lookup"><span data-stu-id="8d5c1-137">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="8d5c1-138">**기타**</span><span class="sxs-lookup"><span data-stu-id="8d5c1-138">**Other**</span></span>|<span data-ttu-id="8d5c1-139">디자이너의 **유형** 열에 있는 정보에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-139">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="8d5c1-140">클래스</span><span class="sxs-lookup"><span data-stu-id="8d5c1-140">Classes</span></span>  
 <span data-ttu-id="8d5c1-141">`My.Resources`개체는 각 리소스 파일을 공유 속성이 있는 클래스로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-141">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="8d5c1-142">클래스 이름은 리소스 파일의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-142">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="8d5c1-143">이전 섹션에서 설명한 것 처럼 리소스 파일의 리소스는 클래스에서 속성으로 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-143">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d5c1-144">예제</span><span class="sxs-lookup"><span data-stu-id="8d5c1-144">Example</span></span>  
 <span data-ttu-id="8d5c1-145">이 예제에서는 폼의 제목을 `Form1Title` 응용 프로그램 리소스 파일에 있는 라는 문자열 리소스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-145">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="8d5c1-146">예제가 작동 하려면 응용 프로그램의 리소스 파일에 라는 문자열이 있어야 합니다 `Form1Title` .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-146">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="8d5c1-147">예제</span><span class="sxs-lookup"><span data-stu-id="8d5c1-147">Example</span></span>  
 <span data-ttu-id="8d5c1-148">이 예제에서는 폼의 아이콘을 `Form1Icon` 응용 프로그램의 리소스 파일에 저장 된 이라는 아이콘으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-148">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="8d5c1-149">예제가 작동 하려면 응용 프로그램의 리소스 파일에 이라는 아이콘이 있어야 합니다 `Form1Icon` .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-149">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="8d5c1-150">예제</span><span class="sxs-lookup"><span data-stu-id="8d5c1-150">Example</span></span>  
 <span data-ttu-id="8d5c1-151">이 예제에서는 폼의 배경 이미지를 `Form1Background` 응용 프로그램 리소스 파일에 있는 이라는 이미지 리소스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-151">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="8d5c1-152">이 예제가 작동 하려면 응용 프로그램에 리소스 파일에 라는 이미지 리소스가 있어야 합니다 `Form1Background` .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-152">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="8d5c1-153">예제</span><span class="sxs-lookup"><span data-stu-id="8d5c1-153">Example</span></span>  
 <span data-ttu-id="8d5c1-154">이 예제에서는 `Form1Greeting` 응용 프로그램의 리소스 파일에 이라는 오디오 리소스로 저장 된 소리를 재생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-154">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="8d5c1-155">예제가 작동 하려면 응용 프로그램에 리소스 파일에 이라는 오디오 리소스가 있어야 합니다 `Form1Greeting` .</span><span class="sxs-lookup"><span data-stu-id="8d5c1-155">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="8d5c1-156">`My.Computer.Audio.Play`메서드는 Windows Forms 응용 프로그램에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-156">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="8d5c1-157">예제</span><span class="sxs-lookup"><span data-stu-id="8d5c1-157">Example</span></span>  
 <span data-ttu-id="8d5c1-158">이 예제에서는 응용 프로그램의 문자열 리소스에 대 한 프랑스어 문화권 버전을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-158">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="8d5c1-159">리소스의 이름은 `Message` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-159">The resource is named `Message`.</span></span> <span data-ttu-id="8d5c1-160">개체가 사용 하는 문화권을 변경 하기 위해 `My.Resources` 이 예제에서는를 사용 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-160">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="8d5c1-161">이 예제가 작동 하려면 응용 프로그램의 리소스 파일에 라는 문자열이 있어야 `Message` 하 고 응용 프로그램에는 해당 리소스 파일 Resources.fr의 프랑스어 문화권 버전이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-161">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="8d5c1-162">응용 프로그램에 프랑스어 문화권 버전의 리소스 파일이 없는 경우 `My.Resource` 개체는 기본 문화권 리소스 파일에서 리소스를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d5c1-162">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="8d5c1-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d5c1-163">See also</span></span>

- [<span data-ttu-id="8d5c1-164">애플리케이션 리소스 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="8d5c1-164">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)
- [<span data-ttu-id="8d5c1-165">데스크톱 앱의 리소스</span><span class="sxs-lookup"><span data-stu-id="8d5c1-165">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)
