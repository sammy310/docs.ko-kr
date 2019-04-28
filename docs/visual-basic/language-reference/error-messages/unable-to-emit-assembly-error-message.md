---
title: 어셈블리를 생성할 수 없습니다. <error message>
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: d564f4f4462a691504297d65575956c5f06691ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936281"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="909e3-102">어셈블리를 생성할 수 없습니다: \<오류 메시지 ></span><span class="sxs-lookup"><span data-stu-id="909e3-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="909e3-103">Visual Basic 컴파일러에서 어셈블리 링커 호출 (*Al.exe*, Alink 라고도) 매니페스트와 링커를 사용 하 여 어셈블리를 생성할 어셈블리를 만들 때의 내보내기 단계에서 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="909e3-104">**오류 ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="909e3-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="909e3-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="909e3-105">To correct this error</span></span>

1. <span data-ttu-id="909e3-106">따옴표 붙은 오류 메시지를 확인 하 고 항목을 참조 하십시오 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) 추가 설명과 권장 사항을 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="909e3-107">어셈블리 중 하나를 사용 하 여 수동으로 로그인을 시도 합니다 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) 또는 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="909e3-108">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="909e3-109">어셈블리에 수동으로 서명하려면</span><span class="sxs-lookup"><span data-stu-id="909e3-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="909e3-110">사용 된 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)) 공개/개인 키 쌍 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="909e3-111">이 파일에는 *.snk* 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="909e3-112">프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="909e3-113">엽니다는 [Visual Studio 용 개발자 명령 프롬프트](../../../framework/tools/developer-command-prompt-for-vs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="909e3-114">Windows 10에서 입력 **개발자 명령 프롬프트** 작업 표시줄에서 검색 상자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="909e3-115">그런 다음 선택 **VS 2017 용 개발자 명령 프롬프트** 결과 목록에서.</span><span class="sxs-lookup"><span data-stu-id="909e3-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="909e3-116">어셈블리 래퍼를 배치 하려는 디렉터리로 디렉터리를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="909e3-117">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="909e3-118">입력할 수 있는 실제 명령의 예로:</span><span class="sxs-lookup"><span data-stu-id="909e3-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="909e3-119">경로 또는 파일에 공백이 있으면 큰따옴표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="909e3-120">Visual Studio의 방금 만든 파일에 대 한.NET 어셈블리 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="909e3-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="909e3-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="909e3-121">See also</span></span>

- [<span data-ttu-id="909e3-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="909e3-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="909e3-123">Sn.exe(강력한 이름 도구)</span><span class="sxs-lookup"><span data-stu-id="909e3-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="909e3-124">방법: 공개/개인 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="909e3-124">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="909e3-125">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="909e3-125">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)