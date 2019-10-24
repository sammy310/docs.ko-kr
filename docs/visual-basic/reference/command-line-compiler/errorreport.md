---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: a9741f7a8283f8603e02dae5abea151c6ee5d75e
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775662"
---
# <a name="-errorreport"></a><span data-ttu-id="cbc17-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="cbc17-102">-errorreport</span></span>

<span data-ttu-id="cbc17-103">Visual Basic 컴파일러에서 내부 컴파일러 오류를 보고 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbc17-104">구문</span><span class="sxs-lookup"><span data-stu-id="cbc17-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="cbc17-105">주의</span><span class="sxs-lookup"><span data-stu-id="cbc17-105">Remarks</span></span>

<span data-ttu-id="cbc17-106">이 옵션은 Microsoft의 Visual Basic 팀에 Visual Basic ICE (내부 컴파일러 오류)를 보고 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="cbc17-107">기본적으로 컴파일러는 Microsoft에 정보를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="cbc17-108">그러나 내부 컴파일러 오류가 발생 하는 경우이 옵션을 사용 하면 오류를 Microsoft에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="cbc17-109">이 정보는 Microsoft 엔지니어가 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="cbc17-110">사용자는 컴퓨터 및 사용자 정책 권한에 따라 보고서를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="cbc17-111">다음 표에서는 `-errorreport` 옵션의 효과를 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="cbc17-112">옵션</span><span class="sxs-lookup"><span data-stu-id="cbc17-112">Option</span></span>|<span data-ttu-id="cbc17-113">동작</span><span class="sxs-lookup"><span data-stu-id="cbc17-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="cbc17-114">내부 컴파일러 오류가 발생 하는 경우 컴파일러에서 수집한 정확한 데이터를 볼 수 있는 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="cbc17-115">오류 보고서에 중요 한 정보가 있는지 확인 하 고 Microsoft로 보낼지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="cbc17-116">이를 전송 하기로 결정 하 고 컴퓨터 및 사용자 정책 설정에서 허용 하는 경우 컴파일러는 데이터를 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="cbc17-117">오류 보고서를 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-117">Queues the error report.</span></span> <span data-ttu-id="cbc17-118">관리자 권한으로 로그인 하는 경우 마지막으로 로그인 한 이후에 발생 한 모든 오류를 보고할 수 있습니다 (오류에 대 한 보고서를 3 일 마다 한 번만 보낼지 묻는 메시지는 표시 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="cbc17-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="cbc17-119">이는 `-errorreport` 옵션이 지정 되지 않은 경우의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="cbc17-120">내부 컴파일러 오류가 발생 하 고 컴퓨터 및 사용자 정책 설정에서 허용 하는 경우 컴파일러는 데이터를 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="cbc17-121">@No__t_0 옵션은 [Windows 오류 보고](/windows/desktop/wer/windows-error-reporting) 시스템 설정에서 보고를 사용 하도록 설정한 경우 오류 정보를 자동으로 Microsoft에 보내도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="cbc17-122">내부 컴파일러 오류가 발생 하면 수집 되거나 Microsoft로 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="cbc17-123">컴파일러는 일반적으로 일부 소스 코드를 포함 하는 오류가 발생 했을 때 스택을 포함 하는 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="cbc17-124">[-@No__t_0 보고서](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션과 함께 사용 하는 경우 전체 원본 파일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="cbc17-125">이 옵션은 Microsoft 엔지니어가 오류를 보다 쉽게 재현할 수 있도록-문제가 있는 [보고서](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션과 함께 사용 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-125">This option is best used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="cbc17-126">@No__t_0 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="cbc17-127">예제</span><span class="sxs-lookup"><span data-stu-id="cbc17-127">Example</span></span>

<span data-ttu-id="cbc17-128">다음 코드는 `T2.vb`를 컴파일하려고 시도 하 고, 컴파일러에서 내부 컴파일러 오류가 발생 하는 경우 오류 보고서를 Microsoft로 보낼지 묻는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc17-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="cbc17-129">참조</span><span class="sxs-lookup"><span data-stu-id="cbc17-129">See also</span></span>

- [<span data-ttu-id="cbc17-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="cbc17-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cbc17-131">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="cbc17-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="cbc17-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="cbc17-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
