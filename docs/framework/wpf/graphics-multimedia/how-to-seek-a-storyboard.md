---
title: '방법: 스토리보드 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: a57272c17a5bc6f5baaa21fb77233fc5693d1914
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131666"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="85650-102">방법: 스토리보드 검색</span><span class="sxs-lookup"><span data-stu-id="85650-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="85650-103">다음 예제에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드를 <xref:System.Windows.Media.Animation.Storyboard> storyboard 애니메이션에서 임의 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85650-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85650-104">예제</span><span class="sxs-lookup"><span data-stu-id="85650-104">Example</span></span>  
 <span data-ttu-id="85650-105">다음은 샘플에 대한 XAML 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="85650-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="85650-106">예제</span><span class="sxs-lookup"><span data-stu-id="85650-106">Example</span></span>  
 <span data-ttu-id="85650-107">다음은 위의 XAML 코드와 함께 사용되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="85650-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="85650-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="85650-108">See also</span></span>

- [<span data-ttu-id="85650-109">동기적으로 Storyboard 검색</span><span class="sxs-lookup"><span data-stu-id="85650-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
