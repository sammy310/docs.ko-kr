---
description: '자세한 정보: 소리 재생(Visual Basic)'
title: 소리 재생
ms.date: 07/20/2015
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
ms.openlocfilehash: 247af8274108ca8374cf87e53aa2aaad8e5e736c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641514"
---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="af796-103">소리 재생(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af796-103">Playing Sounds (Visual Basic)</span></span>

<span data-ttu-id="af796-104">`My.Computer.Audio` 개체는 소리 재생 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-104">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="af796-105">소리 재생</span><span class="sxs-lookup"><span data-stu-id="af796-105">Playing Sounds</span></span>  

 <span data-ttu-id="af796-106">백그라운드 재생을 사용하면 애플리케이션이 소리가 재생되는 동안 다른 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-106">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="af796-107">`My.Computer.Audio.Play` 메서드를 사용하면 애플리케이션이 한 번에 하나의 배경 소리만 재생할 수 있습니다. 애플리케이션이 새 배경 소리를 재생하는 경우 이전 배경 소리의 재생을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-107">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="af796-108">소리를 재생하고 완료될 때까지 기다릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-108">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="af796-109">다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-109">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="af796-110">`AudioPlayMode.WaitToComplete`를 지정하면 `My.Computer.Audio.Play`는 호출하는 코드가 계속되기 전에 소리가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="af796-110">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="af796-111">이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-111">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 <span data-ttu-id="af796-112">다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-112">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="af796-113">이 예제를 사용하는 경우 애플리케이션 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-113">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="af796-114">소리 반복 재생</span><span class="sxs-lookup"><span data-stu-id="af796-114">Playing Looping Sounds</span></span>  

 <span data-ttu-id="af796-115">다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-115">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="af796-116">이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-116">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 <span data-ttu-id="af796-117">다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-117">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="af796-118">이 예제를 사용하는 경우 애플리케이션 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-118">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 <span data-ttu-id="af796-119">앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-119">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="af796-120">코드 조각 선택에서 **Windows Forms 애플리케이션 &gt; 소리** 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-120">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="af796-121">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af796-121">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="af796-122">일반적으로 애플리케이션이 소리를 반복 재생하는 경우 결국 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="af796-122">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="af796-123">백그라운드에서 소리 재생 중지</span><span class="sxs-lookup"><span data-stu-id="af796-123">Stopping the Playing of Sounds in the Background</span></span>  

 <span data-ttu-id="af796-124">`My.Computer.Audio.Stop` 메서드를 사용하여 애플리케이션이 백그라운드에서 현재 재생 중인 소리나 소리 반복 재생을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-124">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="af796-125">일반적으로 애플리케이션이 소리를 반복 재생하는 경우 어느 시점에 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="af796-125">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="af796-126">다음 예제에서는 백그라운드에서 재생 중인 소리를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-126">The following example stops a sound that is playing in the background.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 <span data-ttu-id="af796-127">앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-127">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="af796-128">코드 조각 선택에서 **Windows Forms 애플리케이션 &gt; 소리** 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-128">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="af796-129">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af796-129">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="af796-130">시스템 소리 재생</span><span class="sxs-lookup"><span data-stu-id="af796-130">Playing System Sounds</span></span>  

 <span data-ttu-id="af796-131">`My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 지정된 시스템 소리를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af796-131">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="af796-132">`My.Computer.Audio.PlaySystemSound` 메서드는 <xref:System.Media.SystemSound> 클래스의 공유 멤버 중 하나를 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-132">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="af796-133">시스템 소리 <xref:System.Media.SystemSounds.Asterisk%2A>는 일반적으로 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af796-133">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="af796-134">다음 예제에서는 `My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 시스템 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="af796-134">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="af796-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af796-135">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
