---
title: 지역화
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 89851c42570f301bee8a3eca744eb5d069347d4e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120858"
---
# <a name="localization"></a><span data-ttu-id="0ff79-102">지역화</span><span class="sxs-lookup"><span data-stu-id="0ff79-102">Localization</span></span>

<span data-ttu-id="0ff79-103">지역화는 애플리케이션에서 지원할 각 문화권에 맞는 지역화된 버전으로 애플리케이션 리소스를 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="0ff79-104">[지역화 가능성 검토](../../../docs/standard/globalization-localization/localizability-review.md) 단계를 완료한 후에만 지역화 단계를 진행하여 전역화된 애플리케이션이 지역화 준비가 되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>

<span data-ttu-id="0ff79-105">지역화할 준비가 된 애플리케이션은 모든 사용자 인터페이스 요소가 포함된 블록 및 실행 코드가 포함된 블록이라는 두 가지 개념 블록으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-105">An application that is ready for localization is separated into two conceptual blocks: a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="0ff79-106">사용자 인터페이스 블록에는 중립적인 문화권에 적용할 수 있는 문자열, 오류 메시지, 대화 상자, 메뉴, 포함 개체 리소스 등과 같은 지역화 가능한 사용자 인터페이스 요소만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="0ff79-107">코드 블록에는 지원되는 모든 문화권에서 사용할 애플리케이션 코드만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="0ff79-108">공용 언어 런타임은 해당 리소스에서 애플리케이션의 실행 코드를 분리하는 위성 어셈블리 리소스 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="0ff79-109">이 모델을 구현하는 방법에 대한 자세한 내용은 [.NET의 리소스](../../../docs/framework/resources/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ff79-109">For more information about implementing this model, see [Resources in .NET](../../../docs/framework/resources/index.md).</span></span>

<span data-ttu-id="0ff79-110">애플리케이션의 지역화된 버전 각각에 대해 대상 문화권의 적절한 언어로 번역된 지역화된 사용자 인터페이스 블록을 포함한 새 위성 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="0ff79-111">모든 문화권의 코드 블록은 동일하게 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="0ff79-112">지역화된 버전의 사용자 인터페이스 블록과 코드 블록을 조합하면 애플리케이션의 지역화된 버전이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>

<span data-ttu-id="0ff79-113">Windows SDK(Software Development Kit)에서는 대상 문화권에 대한 Windows Forms를 빠르게 지역화할 수 있게 하는 Windows Forms 리소스 편집기(Winres.exe)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff79-113">The Windows Software Development Kit (SDK) supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="0ff79-114">이 도구 사용에 대한 자세한 내용은 [Winres.exe(Windows Forms 리소스 편집기)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ff79-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ff79-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ff79-115">See also</span></span>

- [<span data-ttu-id="0ff79-116">전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="0ff79-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)
- [<span data-ttu-id="0ff79-117">지역화 가능성 검토</span><span class="sxs-lookup"><span data-stu-id="0ff79-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)
- [<span data-ttu-id="0ff79-118">전역화</span><span class="sxs-lookup"><span data-stu-id="0ff79-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)
- [<span data-ttu-id="0ff79-119">데스크톱 앱의 리소스</span><span class="sxs-lookup"><span data-stu-id="0ff79-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
