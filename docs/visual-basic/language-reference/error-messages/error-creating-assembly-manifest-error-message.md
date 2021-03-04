---
description: '자세히 알아보기: BC30140: 어셈블리 매니페스트를 만드는 동안 오류 발생: <error message>'
title: 어셈블리 매니페스트를 만드는 동안 오류가 발생했습니다. <error message>
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: e2c690ab198e11a70a2fc3bba925ccc4ccb31c79
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103415"
---
# <a name="bc30140-error-creating-assembly-manifest-error-message"></a><span data-ttu-id="b2bee-103">BC30140: 어셈블리 매니페스트를 만드는 동안 오류가 발생 했습니다. \<error message></span><span class="sxs-lookup"><span data-stu-id="b2bee-103">BC30140: Error creating assembly manifest: \<error message></span></span>

<span data-ttu-id="b2bee-104">Visual Basic 컴파일러는 어셈블리 링커 (Al.exe (Alink) 라고도 함)를 호출 하 여 매니페스트로 어셈블리를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bee-104">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="b2bee-105">링커가 어셈블리 만들기의 내보내기 전 단계에서 오류를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2bee-105">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>

 <span data-ttu-id="b2bee-106">지정한 키 파일 또는 키 컨테이너에 문제가 있으면 이러한 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2bee-106">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="b2bee-107">어셈블리에 완전히 서명을 하려면 퍼블릭 키와 프라이빗 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bee-107">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="b2bee-108">어셈블리 서명을 연기하려면 **서명만 연기** 확인란을 선택하고 공개 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bee-108">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="b2bee-109">어셈블리 서명을 연기할 때 프라이빗 키는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2bee-109">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="b2bee-110">자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../standard/assembly/sign-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2bee-110">For more information, see [How to: Sign an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md).</span></span>

 <span data-ttu-id="b2bee-111">**오류 ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="b2bee-111">**Error ID:** BC30140</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b2bee-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b2bee-112">To correct this error</span></span>

1. <span data-ttu-id="b2bee-113">따옴표 붙은 오류 메시지를 검사 하 고 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2bee-113">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="b2bee-114">오류 AL1019 추가 설명 및 조언</span><span class="sxs-lookup"><span data-stu-id="b2bee-114">for error AL1019 further explanation and advice</span></span>

2. <span data-ttu-id="b2bee-115">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b2bee-115">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2bee-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2bee-116">See also</span></span>

- [<span data-ttu-id="b2bee-117">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="b2bee-117">How to: Sign an Assembly with a Strong Name</span></span>](../../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="b2bee-118">프로젝트 디자이너, 서명 페이지</span><span class="sxs-lookup"><span data-stu-id="b2bee-118">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
- [<span data-ttu-id="b2bee-119">Al.exe</span><span class="sxs-lookup"><span data-stu-id="b2bee-119">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="b2bee-120">Visual Studio 피드백 옵션</span><span class="sxs-lookup"><span data-stu-id="b2bee-120">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)
