---
title: '방법: 플랫폼 호출을 사용하여 웨이브 파일 재생 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 6c2313f7b600bc1670c944f6a93868c1bc4c7c16
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039322"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="a1186-102">방법: 플랫폼 호출을 사용하여 웨이브 파일 재생(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a1186-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>

<span data-ttu-id="a1186-103">다음 C# 코드 예제에서는 플랫폼 호출 서비스를 사용하여 Windows 운영 체제에서 .wav 사운드 파일을 재생하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>

## <a name="example"></a><span data-ttu-id="a1186-104">예</span><span class="sxs-lookup"><span data-stu-id="a1186-104">Example</span></span>

<span data-ttu-id="a1186-105">이 예제 코드에서는 <xref:System.Runtime.InteropServices.DllImportAttribute>를 사용하여 `winmm.dll`의 `PlaySound` 메서드 진입점을 `Form1 PlaySound()`로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-105">This example code uses <xref:System.Runtime.InteropServices.DllImportAttribute> to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="a1186-106">이 예제에는 단추를 포함하는 간단한 Windows Form이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="a1186-107">단추를 클릭하면 재생할 파일을 열 수 있도록 표준 Windows <xref:System.Windows.Forms.OpenFileDialog> 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="a1186-108">웨이브 파일을 선택하면 *winmm.dll* 라이브러리의 `PlaySound()` 메서드를 사용하여 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-108">When a wave file is selected, it is played by using the `PlaySound()` method of the *winmm.dll* library.</span></span> <span data-ttu-id="a1186-109">이 메서드에 대한 자세한 내용은 [파형 오디오 파일과 함께 PlaySound 함수 사용](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1186-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="a1186-110">.wav 확장명을 가진 파일을 찾아서 선택한 다음 **열기**를 클릭하여 플랫폼 호출을 통해 웨이브 파일을 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="a1186-111">텍스트 상자에 선택한 파일의 전체 경로가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-111">A text box shows the full path of the file selected.</span></span>

<span data-ttu-id="a1186-112">**파일 열기** 대화 상자가 필터 설정을 통해 .wav 확장명을 가진 파일만 표시하도록 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a><span data-ttu-id="a1186-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a1186-113">Compiling the code</span></span>

1. <span data-ttu-id="a1186-114">Visual Studio에서 새 C# Windows Forms 애플리케이션 프로젝트를 만들고 이름을 **WinSound**로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-114">Create a new C# Windows Forms Application project in Visual Studio and name it **WinSound**.</span></span>

2. <span data-ttu-id="a1186-115">위의 코드를 복사하여 *Form1.cs* 파일 내용에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-115">Copy the code above, and paste it over the contents of the *Form1.cs* file.</span></span>

3. <span data-ttu-id="a1186-116">다음 코드를 복사하여 *Form1.Designer.cs* 파일의 `InitializeComponent()` 메서드에서 기존 코드 뒤에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-116">Copy the following code, and paste it in the *Form1.Designer.cs* file, in the `InitializeComponent()` method, after any existing code.</span></span>

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. <span data-ttu-id="a1186-117">코드를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1186-117">Compile and run the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1186-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1186-118">See also</span></span>

- [<span data-ttu-id="a1186-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a1186-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a1186-120">상호 운용성 개요</span><span class="sxs-lookup"><span data-stu-id="a1186-120">Interoperability Overview</span></span>](interoperability-overview.md)
- [<span data-ttu-id="a1186-121">플랫폼 호출 자세히 보기</span><span class="sxs-lookup"><span data-stu-id="a1186-121">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="a1186-122">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="a1186-122">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
