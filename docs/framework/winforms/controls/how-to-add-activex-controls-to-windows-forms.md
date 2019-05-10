---
title: '방법: Windows Forms에 ActiveX 컨트롤 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 17311adade187ef3c8e4e639299e6c5cbbcd98a9
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210387"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="c26bd-102">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="c26bd-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="c26bd-103">Visual Studio에서 Windows Forms 디자이너는 호스트 Windows Forms 컨트롤을 최적화 하는 동안에 Windows Forms에서 ActiveX 컨트롤을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="c26bd-104">ActiveX 컨트롤에 추가 되 면 Windows Forms에 대 한 성능 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="c26bd-105">ActiveX 컨트롤을 폼에 추가한 해당 도구 상자에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="c26bd-106">자세한 내용은 [사용자 지정 도구 상자 대화 상자, COM 구성 요소](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="c26bd-107">Windows 폼에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="c26bd-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="c26bd-108">Windows 폼에 ActiveX 컨트롤을 추가 하려면 도구 상자에 컨트롤을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="c26bd-109">Visual Studio 프로젝트에서 컨트롤에 대 한 모든 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="c26bd-110">Windows Forms에서 ActiveX 컨트롤을 사용 하 여 때 염두 할 사항에 대 한 자세한 내용은 참조 하세요. [Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항](considerations-when-hosting-an-activex-control-on-a-windows-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c26bd-111">Windows Forms ActiveX 컨트롤 가져오기 (AxImp.exe) ActiveX 동적 링크 라이브러리 가져오기 시 예상 보다 다른 형식의 이벤트 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="c26bd-112">AxImp.exe에서 만든 인수는 다음과 유사한: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`때 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="c26bd-113">주의이 불일치로 해도 코드는 정상적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="c26bd-114">자세한 내용은 참조 하세요 [Windows Forms ActiveX 컨트롤 가져오기 (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c26bd-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c26bd-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="c26bd-115">See also</span></span>

- [<span data-ttu-id="c26bd-116">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c26bd-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="c26bd-117">[여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c26bd-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="c26bd-118">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="c26bd-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="c26bd-119">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="c26bd-119">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="c26bd-120">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="c26bd-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="c26bd-121">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c26bd-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="c26bd-122">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c26bd-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
