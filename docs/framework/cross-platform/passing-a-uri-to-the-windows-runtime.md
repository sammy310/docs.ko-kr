---
description: '자세한 정보: Windows 런타임에 URI 전달'
title: Windows 런타임에 URI 전달
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
ms.openlocfilehash: 918f8ea71f4b23aeaf2a1295f2edd043a73a95ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "102402273"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="90179-103">Windows 런타임에 URI 전달</span><span class="sxs-lookup"><span data-stu-id="90179-103">Passing a URI to the Windows Runtime</span></span>

<span data-ttu-id="90179-104">Windows 런타임 메서드는 절대 URI만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="90179-104">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="90179-105">상대 URI를 Windows 런타임 메서드에 전달하면 <xref:System.ArgumentException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="90179-105">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="90179-106">.NET Framework 코드에서 Windows 런타임을 사용하는 경우 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스가 IntelliSense에 <xref:System.Uri?displayProperty=nameWithType>로 표시되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="90179-106">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="90179-107"><xref:System.Uri?displayProperty=nameWithType> 클래스는 상대 URI를 허용하지만 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90179-107">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="90179-108">이는 Windows 런타임 구성 요소에서 공개하는 메서드의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="90179-108">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="90179-109">구성 요소가 URI를 사용하는 메서드를 노출하면 코드의 서명에 <xref:System.Uri?displayProperty=nameWithType>가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="90179-109">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="90179-110">그러나 구성 요소의 사용자에 대한 시그니처에는 <xref:Windows.Foundation.Uri?displayProperty=nameWithType>가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="90179-110">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="90179-111">구성 요소에 전달된 URI는 절대 URI여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90179-111">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="90179-112">이 항목은 절대 URI를 검색하는 방법과 앱 패키지의 리소스를 참조하는 경우 절대 URI를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90179-112">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="90179-113">절대 URI 검색 및 사용</span><span class="sxs-lookup"><span data-stu-id="90179-113">Detecting and using an absolute URI</span></span>  

<span data-ttu-id="90179-114"><xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> 속성을 사용하여 Windows 런타임에 전달하기 전에 URI가 절대 URI인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="90179-114">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="90179-115">이 속성을 사용하는 것이 <xref:System.ArgumentException> 예외를 catch하고 처리하는 것보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="90179-115">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="90179-116">앱 패키지의 리소스에 절대 URI 사용</span><span class="sxs-lookup"><span data-stu-id="90179-116">Using an absolute URI for a resource in the app package</span></span>  

<span data-ttu-id="90179-117">앱 패키지에 포함된 리소스에 URI를 지정하려면 `ms-appx` 또는 `ms-appx-web` 체계를 사용하여 절대 URI를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90179-117">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="90179-118">다음 예제에서는 XAML과 코드를 둘 다 사용하여 <xref:Windows.UI.Xaml.Controls.WebView> 컨트롤용 <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> 속성과 <xref:Windows.UI.Xaml.Controls.Image> 컨트롤용 <xref:Windows.UI.Xaml.Controls.Image.Source%2A> 속성을 Pages라는 폴더에 포함된 리소스로 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90179-118">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="90179-119">이러한 스키마에 대한 자세한 내용은 Windows 개발자 센터의 [URI 체계](/windows/uwp/app-resources/uri-schemes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90179-119">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90179-120">참조</span><span class="sxs-lookup"><span data-stu-id="90179-120">See also</span></span>

- [<span data-ttu-id="90179-121">Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원</span><span class="sxs-lookup"><span data-stu-id="90179-121">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](support-for-windows-store-apps-and-windows-runtime.md)
