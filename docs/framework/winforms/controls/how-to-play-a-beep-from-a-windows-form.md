---
title: '방법: Windows Form에서 경고음 재생'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: 1a72f88c05fb21c11864058ffbe81c1957525375
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966517"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="0c7a5-102">방법: Windows Form에서 경고음 재생</span><span class="sxs-lookup"><span data-stu-id="0c7a5-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="0c7a5-103">이 예제에서는 런타임에 경고음을 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c7a5-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c7a5-104">예제</span><span class="sxs-lookup"><span data-stu-id="0c7a5-104">Example</span></span>  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="0c7a5-105">C# 코드 샘플에서 재생 되는 소리는 <xref:System.Media.SystemSounds.Beep%2A> 시스템 소리 설정에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c7a5-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="0c7a5-106">자세한 내용은 <xref:System.Media.SystemSounds>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c7a5-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0c7a5-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0c7a5-107">Compiling the Code</span></span>  
 <span data-ttu-id="0c7a5-108">의 C#경우이 예제에는 <xref:System.Media?displayProperty=nameWithType> 네임 스페이스에 대 한 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c7a5-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7a5-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c7a5-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="0c7a5-110">방법: Windows Form에서 시스템 소리 재생</span><span class="sxs-lookup"><span data-stu-id="0c7a5-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="0c7a5-111">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="0c7a5-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
