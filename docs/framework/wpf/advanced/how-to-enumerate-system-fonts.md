---
title: '방법: 시스템 글꼴 열거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: c7e81b5d1b70ba911a0b505219f7977e019038cf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352440"
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="efb4b-102">방법: 시스템 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="efb4b-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="efb4b-103">예제</span><span class="sxs-lookup"><span data-stu-id="efb4b-103">Example</span></span>  
 <span data-ttu-id="efb4b-104">다음 예제에서는 시스템 글꼴 컬렉션의에서 글꼴을 열거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efb4b-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="efb4b-105">각각의 글꼴 패밀리 이름 <xref:System.Windows.Media.FontFamily> 내에서 <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> 콤보 상자에 항목으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb4b-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="efb4b-106">같은 디렉터리에 있는 여러 버전의 동일한 글꼴 패밀리를 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 글꼴 열거형 글꼴의 최신 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb4b-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="efb4b-107">버전 정보를 확인 하지 않습니다, 경우에 최신 타임 스탬프를 사용 하 여 글꼴 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb4b-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="efb4b-108">타임 스탬프 정보를 해당 하는 경우에 알파벳 순서로 첫 번째는 글꼴 파일 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb4b-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
