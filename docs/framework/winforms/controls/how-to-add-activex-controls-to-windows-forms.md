---
title: 양식에 ActiveX 컨트롤 추가
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 920c1111a5703352a4b624068e3d5ceae9892591
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746847"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="f5441-102">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="f5441-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="f5441-103">Visual Studio의 Windows Forms 디자이너은 Windows Forms 컨트롤을 호스팅하도록 최적화 되어 있지만 ActiveX 컨트롤을 Windows Forms에 배치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="f5441-104">ActiveX 컨트롤이 추가 될 때 Windows Forms에 대 한 성능 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="f5441-105">ActiveX 컨트롤을 폼에 추가 하기 전에 도구 상자에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="f5441-106">자세한 내용은 [COM 구성 요소, 도구 상자 사용자 지정 대화 상자](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f5441-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="f5441-107">Windows Form에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="f5441-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="f5441-108">Windows Form에 ActiveX 컨트롤을 추가 하려면 도구 상자에서 컨트롤을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="f5441-109">Visual Studio는 프로젝트의 컨트롤에 대 한 모든 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="f5441-110">Windows Forms에서 ActiveX 컨트롤을 사용할 때 고려해 야 할 사항에 대 한 자세한 내용은 [Windows Form에서 Activex 컨트롤을 호스팅할 때의 고려 사항](considerations-when-hosting-an-activex-control-on-a-windows-form.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f5441-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f5441-111">Activex 컨트롤 가져오기 (Aximp.exe) Windows Forms activex 동적 연결 라이브러리를 가져올 때 예상과 다른 형식의 이벤트 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="f5441-112">Aximp.exe에서 생성 되는 인수는 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` 예상 되는 경우 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="f5441-113">이 irregularity는 코드가 정상적으로 작동 하는 것을 방지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5441-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="f5441-114">자세한 내용은 [Windows Forms ActiveX 컨트롤 가져오기 (aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f5441-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5441-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5441-115">See also</span></span>

- [<span data-ttu-id="f5441-116">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f5441-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="f5441-117">[여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5441-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="f5441-118">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="f5441-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="f5441-119">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="f5441-119">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f5441-120">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f5441-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f5441-121">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f5441-121">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
