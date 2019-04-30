---
title: '방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 110aab0c0826bb4b06e22158afd6af37b5406be4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971199"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="78918-102">방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="78918-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="78918-103">Windows Forms <xref:System.Windows.Forms.Label> 줄 또는 여러 줄 컨트롤 수 있으며 자동으로 크기를 조정할 수에 맞게 해당 캡션 또는 크기가 하거나 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78918-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="78918-104"><xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 사용 하면 컨트롤의 크기를 크게 또는 작게 캡션에 맞게 캡션을 런타임에 변경 될 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78918-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="78918-105">내용에 맞게 동적으로 크기를 조정 레이블 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="78918-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="78918-106">설정 해당 <xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="78918-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="78918-107">하는 경우 <xref:System.Windows.Forms.Label.AutoSize%2A> 로 설정 된 `false`에 지정 된 단어를 <xref:System.Windows.Forms.Label.Text%2A> 속성은 가능한 경우 다음 줄으로 줄 바꿈이 되지만 컨트롤 증가 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78918-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78918-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="78918-108">See also</span></span>

- [<span data-ttu-id="78918-109">방법: Windows Forms Label 컨트롤을 사용 하 여 액세스 키 만들기</span><span class="sxs-lookup"><span data-stu-id="78918-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="78918-110">Label 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="78918-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="78918-111">레이블 컨트롤</span><span class="sxs-lookup"><span data-stu-id="78918-111">Label Control</span></span>](label-control-windows-forms.md)
