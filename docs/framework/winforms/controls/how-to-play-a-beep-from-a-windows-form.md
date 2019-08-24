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
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015819"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="b6c5a-102">방법: Windows Form에서 경고음 재생</span><span class="sxs-lookup"><span data-stu-id="b6c5a-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="b6c5a-103">이 예제에서는 런타임에 경고음을 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6c5a-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="b6c5a-104">예제</span><span class="sxs-lookup"><span data-stu-id="b6c5a-104">Example</span></span>

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
> <span data-ttu-id="b6c5a-105">C# 코드 샘플에서 재생 되는 소리는 <xref:System.Media.SystemSounds.Beep%2A> 시스템 소리 설정에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6c5a-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="b6c5a-106">자세한 내용은 <xref:System.Media.SystemSounds>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6c5a-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="b6c5a-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b6c5a-107">Compiling the Code</span></span>
 <span data-ttu-id="b6c5a-108">의 C#경우이 예제에는 <xref:System.Media?displayProperty=nameWithType> 네임 스페이스에 대 한 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6c5a-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6c5a-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6c5a-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="b6c5a-110">방법: Windows Form에서 시스템 소리 재생</span><span class="sxs-lookup"><span data-stu-id="b6c5a-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="b6c5a-111">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="b6c5a-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
