---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: 5471f0783eee5e2c14cf0f140094d5c292a73756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663260"
---
# <a name="-errorreport"></a><span data-ttu-id="42c81-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="42c81-102">-errorreport</span></span>

<span data-ttu-id="42c81-103">Visual Basic 컴파일러에서 내부 컴파일러 오류를 보고 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="42c81-104">구문</span><span class="sxs-lookup"><span data-stu-id="42c81-104">Syntax</span></span>

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="42c81-105">설명</span><span class="sxs-lookup"><span data-stu-id="42c81-105">Remarks</span></span>

<span data-ttu-id="42c81-106">이 옵션에는 microsoft Visual Basic 팀에 Visual Basic 내부 컴파일러 오류 (ICE)를 보고 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="42c81-107">기본적으로 컴파일러는 Microsoft에 없는 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="42c81-108">그러나 내부 컴파일러 오류가 발생 수행을 하는 경우이 옵션 Microsoft로 오류를 보고 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="42c81-109">이 정보는 Microsoft 엔지니어가 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="42c81-110">보고서를 보내는 사용자의 능력 컴퓨터 및 사용자 정책 권한에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="42c81-111">다음 표에서 요약의 효과 `-errorreport` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="42c81-112">옵션</span><span class="sxs-lookup"><span data-stu-id="42c81-112">Option</span></span>|<span data-ttu-id="42c81-113">동작</span><span class="sxs-lookup"><span data-stu-id="42c81-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="42c81-114">내부 컴파일러 오류가 발생 하는 경우 대화 상자가 나타난 컴파일러에서 수집한 정확한 데이터를 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="42c81-115">오류 보고서에 대 한 중요 한 정보가 있는지 확인 하 고 Microsoft로 보낼지 여부를 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="42c81-116">보내기로 컴퓨터 및 사용자 정책 설정에서 허용 하 고 컴파일러는 데이터를 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="42c81-117">오류 보고서를 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-117">Queues the error report.</span></span> <span data-ttu-id="42c81-118">관리자 권한으로 로그인 하는 경우에 기록 된 마지막 시간 이후 발생 한 모든 오류를 보고할 수 있습니다 (하지 묻는 3 일 마다 한 번에 오류에 대 한 보고서를 보내도록).</span><span class="sxs-lookup"><span data-stu-id="42c81-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="42c81-119">이 기본 동작은 때는 `-errorreport` 옵션이 지정 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="42c81-120">내부 컴파일러 오류가 발생 하 고 컴퓨터 및 사용자 정책 설정에서 허용 하는 경우 컴파일러는 Microsoft로 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="42c81-121">옵션 `-errorreport:send` 하 여 보고를 사용 하는 경우 Microsoft로 오류 정보를 자동으로 보낼 시도 합니다 [Windows 오류 보고](/windows/desktop/wer/windows-error-reporting) 시스템 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="42c81-122">내부 컴파일러 오류가 발생 하는 경우 되거나 되지 않습니다 수 수집 Microsoft로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="42c81-123">컴파일러는 일반적으로 일부 소스 코드를 포함 하는 오류 시 스택을 포함 하는 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="42c81-124">하는 경우 `-errorreport` 사용 되는 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션을 전체 소스 파일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="42c81-125">이 옵션은 사용 하 여 가장 적합 합니다 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션을 자세히 하기 위해 Microsoft 엔지니어가 오류를 쉽게 재현할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="42c81-126">`-errorreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="42c81-127">예제</span><span class="sxs-lookup"><span data-stu-id="42c81-127">Example</span></span>

<span data-ttu-id="42c81-128">다음 코드를 컴파일하려고 시도 `T2.vb`, 한 컴파일러에 내부 컴파일러 오류가 발생 하는 경우 Microsoft로 오류 보고서를 보낼 것인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="42c81-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="42c81-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="42c81-129">See also</span></span>

- [<span data-ttu-id="42c81-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="42c81-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="42c81-131">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="42c81-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="42c81-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="42c81-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
