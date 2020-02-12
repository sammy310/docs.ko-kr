---
title: Windows 런타임에 URI 전달
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
ms.openlocfilehash: 71d427c2d602efbd92dc0128b1fada85a987904a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123625"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="cf967-102">Windows 런타임에 URI 전달</span><span class="sxs-lookup"><span data-stu-id="cf967-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="cf967-103">Windows 런타임 메서드는 절대 URI만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="cf967-104">Windows 런타임 메서드에 상대 URI를 전달 하면 <xref:System.ArgumentException> 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="cf967-105">그 이유는 다음과 같습니다. .NET Framework 코드에서 Windows 런타임를 사용 하는 경우 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스가 Intellisense에서 <xref:System.Uri?displayProperty=nameWithType>로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="cf967-106"><xref:System.Uri?displayProperty=nameWithType> 클래스는 상대 Uri를 허용 하지만 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="cf967-107">Windows 런타임 구성 요소에 노출 하는 방법에도 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="cf967-108">구성 요소가 URI를 사용하는 메서드를 노출하면 코드의 서명에 <xref:System.Uri?displayProperty=nameWithType>가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cf967-109">그러나 구성 요소의 사용자에 게는 <xref:Windows.Foundation.Uri?displayProperty=nameWithType>포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cf967-110">구성 요소에 전달된 URI는 절대 URI여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="cf967-111">이 항목은 절대 URI를 검색하는 방법과 앱 패키지의 리소스를 참조하는 경우 절대 URI를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="cf967-112">절대 URI 검색 및 사용</span><span class="sxs-lookup"><span data-stu-id="cf967-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="cf967-113">Windows 런타임에 전달 하기 전에 URI가 절대 URI 인지 확인 하려면 <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="cf967-114">이 속성을 사용하는 것이 <xref:System.ArgumentException> 예외를 catch하고 처리하는 것보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="cf967-115">앱 패키지의 리소스에 절대 URI 사용</span><span class="sxs-lookup"><span data-stu-id="cf967-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="cf967-116">앱 패키지에 포함된 리소스에 URI를 지정하려면 `ms-appx` 또는 `ms-appx-web` 체계를 사용하여 절대 URI를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="cf967-117">다음 예제에서는 XAML과 코드를 모두 사용 하 여 <xref:Windows.UI.Xaml.Controls.WebView> 컨트롤의 <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> 속성 및 <xref:Windows.UI.Xaml.Controls.Image> 컨트롤의 <xref:Windows.UI.Xaml.Controls.Image.Source%2A> 속성을 Pages 라는 폴더에 포함 된 리소스로 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf967-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="cf967-118">이러한 체계에 대 한 자세한 내용은 Windows 개발자 센터의 [URI 체계](/windows/uwp/app-resources/uri-schemes) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf967-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf967-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf967-119">See also</span></span>

- [<span data-ttu-id="cf967-120">Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원</span><span class="sxs-lookup"><span data-stu-id="cf967-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
