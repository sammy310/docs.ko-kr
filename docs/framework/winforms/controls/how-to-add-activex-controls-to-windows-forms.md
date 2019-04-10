---
title: '방법: Windows Forms에 ActiveX 컨트롤 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166052"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="399b2-102">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="399b2-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="399b2-103">Windows Forms 디자이너는 호스트 Windows Forms 컨트롤을 최적화 하는 동안에 Windows Forms에서 ActiveX 컨트롤을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="399b2-104">ActiveX 컨트롤에 추가 되 면 Windows Forms에 대 한 성능 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="399b2-105">ActiveX 컨트롤을 폼에 추가한 해당 도구 상자에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="399b2-106">자세한 내용은 [사용자 지정 도구 상자 대화 상자, COM 구성 요소](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="399b2-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="399b2-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="399b2-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="399b2-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="399b2-110">Windows 폼에 ActiveX 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="399b2-110">To add an ActiveX control to your Windows Form</span></span>  
  
-   <span data-ttu-id="399b2-111">도구 상자 컨트롤을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-111">Double-click the control on the Toolbox.</span></span>  
  
     <span data-ttu-id="399b2-112">Visual Studio 프로젝트에서 컨트롤에 대 한 모든 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-112">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="399b2-113">Windows Forms에서 ActiveX 컨트롤을 사용 하 여 때 염두 할 사항에 대 한 자세한 내용은 참조 하세요. [Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항](considerations-when-hosting-an-activex-control-on-a-windows-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="399b2-114">Windows Forms ActiveX 컨트롤 가져오기 (AxImp.exe) ActiveX 동적 링크 라이브러리 가져오기 시 예상 보다 다른 형식의 이벤트 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="399b2-115">AxImp.exe에서 만든 인수는 다음과 유사한: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`때 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="399b2-116">주의이 불일치로 해도 코드는 정상적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="399b2-117">자세한 내용은 참조 하세요 [Windows Forms ActiveX 컨트롤 가져오기 (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="399b2-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399b2-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="399b2-118">See also</span></span>

- [<span data-ttu-id="399b2-119">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="399b2-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="399b2-120">여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교</span><span class="sxs-lookup"><span data-stu-id="399b2-120">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [<span data-ttu-id="399b2-121">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="399b2-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="399b2-122">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="399b2-122">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="399b2-123">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="399b2-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="399b2-124">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="399b2-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="399b2-125">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="399b2-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
