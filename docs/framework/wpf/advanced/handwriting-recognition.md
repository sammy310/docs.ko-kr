---
title: 필기 인식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 417af272514ac9ce68c8faa72339f2befc2dd7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923385"
---
# <a name="handwriting-recognition"></a><span data-ttu-id="03d57-102">필기 인식</span><span class="sxs-lookup"><span data-stu-id="03d57-102">Handwriting Recognition</span></span>
<span data-ttu-id="03d57-103">이 섹션에서는 WPF 플랫폼의 디지털 링크에 관련되므로 인식의 기본 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="03d57-104">인식 솔루션</span><span class="sxs-lookup"><span data-stu-id="03d57-104">Recognition Solutions</span></span>  
 <span data-ttu-id="03d57-105">다음 예에서는 [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) 클래스를 사용하여 잉크를 인식하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03d57-106">이 샘플에서는 필기 인식기를 시스템에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="03d57-107">**InkRecognition**라는 새 WPF 응용 프로그램 프로젝트를 Visual Studio에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="03d57-108">Window1.xaml 파일의 콘텐츠를 다음 XAML 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="03d57-109">이 코드는 애플리케이션의 사용자 인터페이스를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="03d57-110">\Program Files\Common Files\Microsoft Shared\Ink에 있는 Microsoft Ink 어셈블리, Microsoft.Ink.dll에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="03d57-111">파일의 기반이 되는 코드의 콘텐츠를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="03d57-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="03d57-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="03d57-112">See also</span></span>

- <span data-ttu-id="03d57-113">[Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="03d57-113">[Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span></span>
