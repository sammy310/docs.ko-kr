---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: b6a1c8fce17e3e5a54366c2ff4dff4e6aa668f56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408662"
---
# <a name="-errorreport"></a><span data-ttu-id="910c1-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="910c1-102">-errorreport</span></span>

<span data-ttu-id="910c1-103">Visual Basic 컴파일러에서 내부 컴파일러 오류를 보고하는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="910c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="910c1-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="910c1-105">설명</span><span class="sxs-lookup"><span data-stu-id="910c1-105">Remarks</span></span>

<span data-ttu-id="910c1-106">이 옵션은 Microsoft Visual Basic 팀에 Visual Basic ICE(내부 컴파일러 오류)를 보고하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="910c1-107">기본적으로 컴파일러는 Microsoft에 정보를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="910c1-108">그러나 내부 컴파일러 오류가 발생하는 경우 이 옵션을 사용하면 Microsoft에 오류를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="910c1-109">이 정보는 Microsoft 엔지니어가 원인을 파악하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="910c1-110">사용자가 보고서를 보내는 능력은 컴퓨터 및 사용자 정책 권한에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="910c1-111">다음 표에는 `-errorreport` 옵션의 영향이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="910c1-112">옵션</span><span class="sxs-lookup"><span data-stu-id="910c1-112">Option</span></span>|<span data-ttu-id="910c1-113">동작</span><span class="sxs-lookup"><span data-stu-id="910c1-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="910c1-114">내부 컴파일러 오류가 발생하는 경우 컴파일러에서 수집한 정확한 데이터를 볼 수 있도록 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="910c1-115">오류 보고서에 중요한 정보가 있는지 확인하고 Microsoft로 전송할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="910c1-116">보고서를 전송하기로 결정하고 컴퓨터 및 사용자 정책 설정에서 허용하는 경우 컴파일러는 데이터를 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="910c1-117">오류 보고서를 큐에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-117">Queues the error report.</span></span> <span data-ttu-id="910c1-118">관리자 권한으로 로그인하는 경우 마지막으로 로그인한 이후에 발생한 모든 오류를 보고할 수 있습니다(오류 보고서를 3일마다 한 번 이상 보낼지 묻는 메시지는 표시되지 않음).</span><span class="sxs-lookup"><span data-stu-id="910c1-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="910c1-119">`-errorreport` 옵션이 지정되지 않은 경우 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="910c1-120">내부 컴파일러 오류가 발생하고 컴퓨터 및 사용자 정책 설정에서 허용하는 경우 컴파일러는 데이터를 Microsoft로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="910c1-121">[Windows 오류 보고](/windows/desktop/wer/windows-error-reporting) 시스템 설정에서 보고 기능을 사용하도록 설정한 경우 `-errorreport:send` 옵션은 자동으로 Microsoft에 오류 정보를 전송하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="910c1-122">내부 컴파일러 오류가 발생하는 경우 오류를 수집하거나 Microsoft로 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="910c1-123">컴파일러는 오류가 발생했을 때 스택을 포함하는 데이터를 보냅니다(일반적으로 일부 소스 코드가 포함됨).</span><span class="sxs-lookup"><span data-stu-id="910c1-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="910c1-124">`-errorreport`를 [-bugreport](bugreport.md) 옵션과 함께 사용하는 경우 전체 소스 파일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-124">If `-errorreport` is used with the [-bugreport](bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="910c1-125">이 옵션은 [-bugreport](bugreport.md) 옵션과 함께 사용하는 것이 가장 좋습니다. Microsoft 엔지니어가 오류를 보다 쉽게 재현할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-125">This option is best used with the [-bugreport](bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="910c1-126">Visual Studio 개발 환경 내에서는 `-errorreport` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="910c1-127">예제</span><span class="sxs-lookup"><span data-stu-id="910c1-127">Example</span></span>

<span data-ttu-id="910c1-128">다음 코드는 `T2.vb`를 컴파일하려고 시도하고, 컴파일러에서 내부 컴파일러 오류가 발생하는 경우 오류 보고서를 Microsoft로 보낼지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="910c1-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="910c1-129">참조</span><span class="sxs-lookup"><span data-stu-id="910c1-129">See also</span></span>

- [<span data-ttu-id="910c1-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="910c1-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="910c1-131">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="910c1-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="910c1-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="910c1-132">-bugreport</span></span>](bugreport.md)
