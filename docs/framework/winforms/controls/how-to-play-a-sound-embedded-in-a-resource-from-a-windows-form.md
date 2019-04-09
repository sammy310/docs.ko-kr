---
title: '방법: Windows Form에서 리소스에 포함된 소리 재생'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: 49235f9cb035c5a09c26b427f855fc00e818fe1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078579"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="19b54-102">방법: Windows Form에서 리소스에 포함된 소리 재생</span><span class="sxs-lookup"><span data-stu-id="19b54-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="19b54-103">사용할 수는 <xref:System.Media.SoundPlayer> 포함된 리소스에서 소리를 재생 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="19b54-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19b54-104">예제</span><span class="sxs-lookup"><span data-stu-id="19b54-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19b54-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="19b54-105">Compiling the Code</span></span>  
 <span data-ttu-id="19b54-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19b54-106">This example requires:</span></span>  
  
 <span data-ttu-id="19b54-107">가져오기는 <xref:System.Media?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="19b54-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="19b54-108">프로젝트에 사운드 파일을 포함된 리소스로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="19b54-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="19b54-109">"\<AssemblyName>"을 사운드 파일이 포함된 어셈블리의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="19b54-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="19b54-110">".dll" 접미사는 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="19b54-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19b54-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="19b54-111">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="19b54-112">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="19b54-112">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="19b54-113">방법: Windows Form에서 재생되는 소리 반복</span><span class="sxs-lookup"><span data-stu-id="19b54-113">How to: Loop a Sound Playing on a Windows Form</span></span>](how-to-loop-a-sound-playing-on-a-windows-form.md)
