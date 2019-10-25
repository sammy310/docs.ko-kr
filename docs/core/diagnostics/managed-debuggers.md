---
title: 관리형 디버거 - .NET Core
description: Visual Studio 및 Visual Studio Code 관리형 디버거의 개요입니다.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.openlocfilehash: 3741011d22ab6c4240b7f88a9ab790ea61ecd0d2
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "72303649"
---
# <a name="net-core-managed-debuggers"></a><span data-ttu-id="f7284-103">.NET Core 관리형 디버거</span><span class="sxs-lookup"><span data-stu-id="f7284-103">.NET Core managed debuggers</span></span>

<span data-ttu-id="f7284-104">디버거를 사용하면 프로그램을 일시 중지하거나 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-104">Debuggers allow programs to be paused or executed step-by-step.</span></span> <span data-ttu-id="f7284-105">일시 중지되면 프로세스의 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-105">When paused, the current state of the process can be viewed.</span></span> <span data-ttu-id="f7284-106">주요 섹션을 단계별로 실행하여 코드를 이해하고 그 결과를 생성하는 이유를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-106">By stepping through key sections, you gain understanding of your code and why it produces the result that it does.</span></span>

<span data-ttu-id="f7284-107">Microsoft는 **Visual Studio** 및 **Visual Studio Code**에서 관리 코드에 대한 디버거를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-107">Microsoft provides debuggers for managed code in **Visual Studio** and **Visual Studio Code**.</span></span>

## <a name="visual-studio-managed-debugger"></a><span data-ttu-id="f7284-108">Visual Studio 관리형 디버거</span><span class="sxs-lookup"><span data-stu-id="f7284-108">Visual Studio managed debugger</span></span>

<span data-ttu-id="f7284-109">**Visual Studio**는 가장 포괄적인 디버거를 사용할 수 있는 통합 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-109">**Visual Studio** is an integrated development environment with the most comprehensive debugger available.</span></span> <span data-ttu-id="f7284-110">Visual Studio는 Windows에서 작업하는 개발자에게 탁월한 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-110">Visual Studio is an excellent choice for developers working on Windows.</span></span>

- [<span data-ttu-id="f7284-111">자습서 - Visual Studio를 사용하여 Windows에서 .NET Core 애플리케이션 디버깅</span><span class="sxs-lookup"><span data-stu-id="f7284-111">Tutorial - Debugging a .NET Core application on Windows with Visual Studio</span></span>](../tutorials/debugging-with-visual-studio.md)

<span data-ttu-id="f7284-112">Visual Studio는 Windows 애플리케이션이지만, Linux 및 macOS 앱을 원격으로 디버그하는 데 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-112">While Visual Studio is a Windows application, it can still be used to debug Linux and macOS apps remotely.</span></span>

- [<span data-ttu-id="f7284-113">Visual Studio를 사용하여 Linux/OSX에서 .NET Core 애플리케이션 디버깅</span><span class="sxs-lookup"><span data-stu-id="f7284-113">Debugging a .NET Core application on Linux/OSX with Visual Studio</span></span>](https://github.com/Microsoft/MIEngine/wiki/Offroad-Debugging-of-.NET-Core-on-Linux---OSX-from-Visual-Studio)

 <span data-ttu-id="f7284-114">ASP.NET Core 앱을 디버깅하려면 약간 다른 지침이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-114">Debugging ASP.NET Core apps require slightly different instructions.</span></span>

- [<span data-ttu-id="f7284-115">Visual Studio에서 ASP.NET Core 앱 디버그</span><span class="sxs-lookup"><span data-stu-id="f7284-115">Debug ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications#debug-aspnet-core-apps)

## <a name="visual-studio-code-managed-debugger"></a><span data-ttu-id="f7284-116">Visual Studio Code 관리형 디버거</span><span class="sxs-lookup"><span data-stu-id="f7284-116">Visual Studio Code managed debugger</span></span>

<span data-ttu-id="f7284-117">**Visual Studio Code**는 간단한 플랫폼 간 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-117">**Visual Studio Code** is a lightweight cross-platform code editor.</span></span> <span data-ttu-id="f7284-118">Visual Studio와 동일한 .NET Core 디버거 구현을 사용하지만 사용자 인터페이스가 간소화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7284-118">It uses the same .NET Core debugger implementation as Visual Studio, but with a simplified user interface.</span></span>

- [<span data-ttu-id="f7284-119">자습서 - Visual Studio Code를 사용하여 .NET Core 애플리케이션 디버깅</span><span class="sxs-lookup"><span data-stu-id="f7284-119">Tutorial - Debugging a .NET Core application with Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md#debug)
- [<span data-ttu-id="f7284-120">Visual Studio Code의 디버깅</span><span class="sxs-lookup"><span data-stu-id="f7284-120">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)
