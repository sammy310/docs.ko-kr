---
title: '방법: 동기적으로 Storyboard 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- seeking Storyboards synchronously [WPF]
- Storyboards [WPF], seeking synchronously
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
ms.openlocfilehash: 8ac55346ac83ee94318de90655bde6053ef20687
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371322"
---
# <a name="how-to-seek-a-storyboard-synchronously"></a><span data-ttu-id="03c62-102">방법: 동기적으로 Storyboard 검색</span><span class="sxs-lookup"><span data-stu-id="03c62-102">How to: Seek a Storyboard Synchronously</span></span>
<span data-ttu-id="03c62-103">다음 예제에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> 메서드는 <xref:System.Windows.Media.Animation.Storyboard> 동기적으로 storyboard 애니메이션에서 임의 위치로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c62-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to seek to any position in a storyboard animation synchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03c62-104">예제</span><span class="sxs-lookup"><span data-stu-id="03c62-104">Example</span></span>  
 <span data-ttu-id="03c62-105">다음은 샘플에 대한 XAML 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="03c62-105">The following is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="03c62-106">예제</span><span class="sxs-lookup"><span data-stu-id="03c62-106">Example</span></span>  
 <span data-ttu-id="03c62-107">다음은 위의 XAML 코드와 함께 사용되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="03c62-107">The following is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]
