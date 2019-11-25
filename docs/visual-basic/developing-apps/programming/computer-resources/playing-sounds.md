---
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
ms.openlocfilehash: 416fedd011ff35d2b32d1b64932e3908a73ed14e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345517"
---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="52e73-102">소리 재생(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52e73-102">Playing Sounds (Visual Basic)</span></span>

<span data-ttu-id="52e73-103">`My.Computer.Audio` 개체는 소리 재생 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="52e73-104">소리 재생</span><span class="sxs-lookup"><span data-stu-id="52e73-104">Playing Sounds</span></span>  

 <span data-ttu-id="52e73-105">백그라운드 재생을 사용하면 애플리케이션이 소리가 재생되는 동안 다른 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="52e73-106">`My.Computer.Audio.Play` 메서드를 사용하면 애플리케이션이 한 번에 하나의 배경 소리만 재생할 수 있습니다. 애플리케이션이 새 배경 소리를 재생하는 경우 이전 배경 소리의 재생을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="52e73-107">소리를 재생하고 완료될 때까지 기다릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="52e73-108">다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="52e73-109">`AudioPlayMode.WaitToComplete`를 지정하면 `My.Computer.Audio.Play`는 호출하는 코드가 계속되기 전에 소리가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="52e73-110">이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 <span data-ttu-id="52e73-111">다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-111">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="52e73-112">이 예제를 사용하는 경우 애플리케이션 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-112">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="52e73-113">소리 반복 재생</span><span class="sxs-lookup"><span data-stu-id="52e73-113">Playing Looping Sounds</span></span>  

 <span data-ttu-id="52e73-114">다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-114">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="52e73-115">이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-115">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 <span data-ttu-id="52e73-116">다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="52e73-117">이 예제를 사용하는 경우 애플리케이션 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-117">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 <span data-ttu-id="52e73-118">앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-118">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="52e73-119">코드 조각 선택에서 **Windows Forms 애플리케이션 &gt; 소리**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-119">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="52e73-120">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52e73-120">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="52e73-121">일반적으로 애플리케이션이 소리를 반복 재생하는 경우 결국 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-121">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="52e73-122">백그라운드에서 소리 재생 중지</span><span class="sxs-lookup"><span data-stu-id="52e73-122">Stopping the Playing of Sounds in the Background</span></span>  

 <span data-ttu-id="52e73-123">`My.Computer.Audio.Stop` 메서드를 사용하여 애플리케이션이 백그라운드에서 현재 재생 중인 소리나 소리 반복 재생을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-123">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="52e73-124">일반적으로 애플리케이션이 소리를 반복 재생하는 경우 어느 시점에 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-124">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="52e73-125">다음 예제에서는 백그라운드에서 재생 중인 소리를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-125">The following example stops a sound that is playing in the background.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 <span data-ttu-id="52e73-126">앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-126">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="52e73-127">코드 조각 선택에서 **Windows Forms 애플리케이션 &gt; 소리**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-127">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="52e73-128">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52e73-128">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="52e73-129">시스템 소리 재생</span><span class="sxs-lookup"><span data-stu-id="52e73-129">Playing System Sounds</span></span>  

 <span data-ttu-id="52e73-130">`My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 지정된 시스템 소리를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-130">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="52e73-131">`My.Computer.Audio.PlaySystemSound` 메서드는 <xref:System.Media.SystemSound> 클래스의 공유 멤버 중 하나를 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-131">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="52e73-132">시스템 소리 <xref:System.Media.SystemSounds.Asterisk%2A>는 일반적으로 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-132">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="52e73-133">다음 예제에서는 `My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 시스템 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="52e73-133">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="52e73-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52e73-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
