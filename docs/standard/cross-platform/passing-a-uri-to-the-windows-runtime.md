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
ms.openlocfilehash: 7152fb02abf430c0d0e27b82550e4006e3958e93
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288890"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Windows 런타임에 URI 전달
Windows 런타임 메서드는 절대 URI만 허용합니다. Windows 런타임 메서드에 상대 URI를 전달 하면 <xref:System.ArgumentException> 예외가 throw 됩니다. 그 이유는 다음과 같습니다. .NET Framework 코드에서 Windows 런타임 사용 하는 경우 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스는 <xref:System.Uri?displayProperty=nameWithType> Intellisense에서로 나타납니다. <xref:System.Uri?displayProperty=nameWithType>클래스는 상대 uri를 허용 하지만 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스는 그렇지 않습니다. Windows 런타임 구성 요소에 노출 하는 방법에도 해당 합니다. 구성 요소가 URI를 사용하는 메서드를 노출하면 코드의 서명에 <xref:System.Uri?displayProperty=nameWithType>가 포함됩니다. 그러나 구성 요소의 사용자에 게 서명에는가 포함 됩니다 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> . 구성 요소에 전달된 URI는 절대 URI여야 합니다.  
  
이 항목은 절대 URI를 검색하는 방법과 앱 패키지의 리소스를 참조하는 경우 절대 URI를 만드는 방법을 보여 줍니다.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>절대 URI 검색 및 사용  
<xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>URI를 Windows 런타임 전달 하기 전에 URI가 절대 URI 인지 확인 하려면 속성을 사용 합니다. 이 속성을 사용하는 것이 <xref:System.ArgumentException> 예외를 catch하고 처리하는 것보다 효율적입니다.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>앱 패키지의 리소스에 절대 URI 사용  
앱 패키지에 포함된 리소스에 URI를 지정하려면 `ms-appx` 또는 `ms-appx-web` 체계를 사용하여 절대 URI를 생성할 수 있습니다.  
  
다음 예제에서는 <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> <xref:Windows.UI.Xaml.Controls.WebView> <xref:Windows.UI.Xaml.Controls.Image.Source%2A> XAML과 코드를 사용 하 여 컨트롤의 속성과 컨트롤의 속성을 <xref:Windows.UI.Xaml.Controls.Image> 페이지 라는 폴더에 포함 된 리소스로 설정 하는 방법을 보여 줍니다.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
이러한 스키마에 대한 자세한 내용은 Windows 개발자 센터의 [URI 체계](/windows/uwp/app-resources/uri-schemes)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](support-for-windows-store-apps-and-windows-runtime.md)
