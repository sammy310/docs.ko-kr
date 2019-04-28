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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5ce0d4ac2b95dc4d51e785e3a00026f56c13d2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921383"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="81a02-102">Windows 런타임에 URI 전달</span><span class="sxs-lookup"><span data-stu-id="81a02-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="81a02-103">Windows 런타임 메서드는 절대 URI만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="81a02-104">상대 URI를 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 메서드에 전달하면 <xref:System.ArgumentException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="81a02-105">이유는 다음과 같습니다. 사용 하는 경우는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] .NET Framework 코드에서는 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 으로 표시 되는 클래스 <xref:System.Uri?displayProperty=nameWithType> Intellisense에서.</span><span class="sxs-lookup"><span data-stu-id="81a02-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="81a02-106">합니다 <xref:System.Uri?displayProperty=nameWithType> 클래스는 상대 Uri를 허용 하지만 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="81a02-107">이는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소에 노출하는 메서드의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="81a02-108">구성 요소가 URI를 사용하는 메서드를 노출하면 코드의 서명에 <xref:System.Uri?displayProperty=nameWithType>가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="81a02-109">그러나 구성 요소의 사용자에 게는 시그니처에 <xref:Windows.Foundation.Uri?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="81a02-110">구성 요소에 전달된 URI는 절대 URI여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="81a02-111">이 항목은 절대 URI를 검색하는 방법과 앱 패키지의 리소스를 참조하는 경우 절대 URI를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="81a02-112">절대 URI 검색 및 사용</span><span class="sxs-lookup"><span data-stu-id="81a02-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="81a02-113"><xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> 속성을 사용하여 [!INCLUDE[wrt](../../../includes/wrt-md.md)]에 전달하기 전에 URI가 절대 URI인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="81a02-114">이 속성을 사용하는 것이 <xref:System.ArgumentException> 예외를 catch하고 처리하는 것보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="81a02-115">앱 패키지의 리소스에 절대 URI 사용</span><span class="sxs-lookup"><span data-stu-id="81a02-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="81a02-116">앱 패키지에 포함된 리소스에 URI를 지정하려면 `ms-appx` 또는 `ms-appx-web` 체계를 사용하여 절대 URI를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="81a02-117">다음 예제에서는 설정 하는 방법을 보여 줍니다는 <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> 속성에 대 한는 <xref:Windows.UI.Xaml.Controls.WebView> 컨트롤 및 <xref:Windows.UI.Xaml.Controls.Image.Source%2A> 속성에 대 한는 <xref:Windows.UI.Xaml.Controls.Image> XAML 및 코드를 사용 하 여 페이지 라는 폴더에 포함 된 리소스를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="81a02-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="81a02-118">이러한 스키마에 대 한 자세한 내용은 참조 하세요. [URI 체계](/windows/uwp/app-resources/uri-schemes) Windows 개발자 센터에서.</span><span class="sxs-lookup"><span data-stu-id="81a02-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a02-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="81a02-119">See also</span></span>

- [<span data-ttu-id="81a02-120">Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원</span><span class="sxs-lookup"><span data-stu-id="81a02-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
