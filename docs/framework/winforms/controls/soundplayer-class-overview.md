---
title: SoundPlayer 클래스 개요
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195009"
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="f9db2-102">SoundPlayer 클래스 개요</span><span class="sxs-lookup"><span data-stu-id="f9db2-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="f9db2-103"><xref:System.Media.SoundPlayer> 클래스를 사용하여 응용 프로그램에 소리를 쉽게 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="f9db2-104"><xref:System.Media.SoundPlayer> 클래스 UNC 또는 HTTP 위치 또는 리소스에서.wav 형식의 사운드 파일을 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="f9db2-105">또한는 <xref:System.Media.SoundPlayer> 클래스를 사용 하면 비동기적으로 소리를 재생 하거나 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="f9db2-106"><xref:System.Media.SystemSounds> 클래스를 사용하여 경고음을 포함한 일반적인 시스템 소리를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="f9db2-107">일반적으로 사용되는 속성, 메서드 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="f9db2-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="f9db2-108">이름</span><span class="sxs-lookup"><span data-stu-id="f9db2-108">Name</span></span>|<span data-ttu-id="f9db2-109">설명</span><span class="sxs-lookup"><span data-stu-id="f9db2-109">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> <span data-ttu-id="f9db2-110">속성</span><span class="sxs-lookup"><span data-stu-id="f9db2-110">property</span></span>|<span data-ttu-id="f9db2-111">소리의 파일 경로 또는 웹 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="f9db2-112">허용되는 값은 UNC 또는 HTTP일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> <span data-ttu-id="f9db2-113">속성</span><span class="sxs-lookup"><span data-stu-id="f9db2-113">property</span></span>|<span data-ttu-id="f9db2-114">예외를 throw하기 전에 프로그램에서 소리를 로드하기 위해 대기하는 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="f9db2-115">기본값은 10초입니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-115">The default is 10 seconds.</span></span>|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> <span data-ttu-id="f9db2-116">속성</span><span class="sxs-lookup"><span data-stu-id="f9db2-116">property</span></span>|<span data-ttu-id="f9db2-117">소리의 로드를 완료했는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<xref:System.Media.SoundPlayer.Load%2A> <span data-ttu-id="f9db2-118">메서드</span><span class="sxs-lookup"><span data-stu-id="f9db2-118">method</span></span>|<span data-ttu-id="f9db2-119">소리를 동기적으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-119">Loads a sound synchronously.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> <span data-ttu-id="f9db2-120">메서드</span><span class="sxs-lookup"><span data-stu-id="f9db2-120">method</span></span>|<span data-ttu-id="f9db2-121">소리를 비동기적으로 로드하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="f9db2-122">로드가 완료 되 면 발생 합니다 <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<xref:System.Media.SoundPlayer.Play%2A> <span data-ttu-id="f9db2-123">메서드</span><span class="sxs-lookup"><span data-stu-id="f9db2-123">method</span></span>|<span data-ttu-id="f9db2-124">에 지정 된 소리를 재생 합니다 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 새 스레드에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> <span data-ttu-id="f9db2-125">메서드</span><span class="sxs-lookup"><span data-stu-id="f9db2-125">method</span></span>|<span data-ttu-id="f9db2-126">에 지정 된 소리를 재생 합니다 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 현재 스레드의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<xref:System.Media.SoundPlayer.Stop%2A> <span data-ttu-id="f9db2-127">메서드</span><span class="sxs-lookup"><span data-stu-id="f9db2-127">method</span></span>|<span data-ttu-id="f9db2-128">현재 재생 중인 모든 소리를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-128">Stops any sound currently playing.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadCompleted> <span data-ttu-id="f9db2-129">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="f9db2-129">event</span></span>|<span data-ttu-id="f9db2-130">소리의 로드를 시도한 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f9db2-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9db2-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="f9db2-131">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
