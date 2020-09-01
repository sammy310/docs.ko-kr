---
description: C# 컴파일러 옵션
title: C# 컴파일러 옵션
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: bcb246055ecb553bbefad2a0d5c95bf6a083ee6f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125529"
---
# <a name="c-compiler-options"></a><span data-ttu-id="48eab-103">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="48eab-103">C# Compiler Options</span></span>

<span data-ttu-id="48eab-104">컴파일러는 실행 파일(.exe), 동적 연결 라이브러리(.dll) 또는 코드 모듈(.netmodule)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-104">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="48eab-105">모든 컴파일러 옵션은 **-옵션** 및 **/옵션**의 두 가지 형태로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-105">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="48eab-106">문서에는 **-옵션** 양식만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-106">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="48eab-107">Visual Studio에서는 *web.config* 파일에서 컴파일러 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-107">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="48eab-108">자세한 내용은 [\<compiler> 요소](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48eab-108">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="48eab-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="48eab-109">In this section</span></span>

- <span data-ttu-id="48eab-110">[csc.exe를 사용한 명령줄 빌드](command-line-building-with-csc-exe.md) 명령줄에서 Visual C# 애플리케이션을 빌드하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-110">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="48eab-111">[Visual Studio 명령줄에 대한 환경 변수 설정 방법](how-to-set-environment-variables-for-the-visual-studio-command-line.md)*vsvars32.bat*를 실행하여 명령줄 빌드를 사용하도록 설정하는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-111">[How to set environment variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *vsvars32.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="48eab-112">[C# 컴파일러 옵션 범주별 목록](listed-by-category.md) 컴파일러 옵션의 범주별 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-112">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="48eab-113">[C# 컴파일러 옵션 사전순 목록](listed-alphabetically.md) 컴파일러 옵션의 사전순 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-113">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="48eab-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="48eab-114">Related sections</span></span>

- <span data-ttu-id="48eab-115">[프로젝트 디자이너, 빌드 페이지](/visualstudio/ide/reference/build-page-project-designer-csharp) 프로젝트가 컴파일, 빌드 및 디버그되는 방법을 제어하는 속성 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-115">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="48eab-116">Visual C# 프로젝트의 사용자 지정 빌드 단계에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-116">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="48eab-117">[기본 및 사용자 지정 빌드](/visualstudio/ide/compiling-and-building-in-visual-studio) 빌드 형식 및 구성에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-117">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="48eab-118">[빌드 준비 및 관리](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Visual Studio 개발 환경 내의 빌드 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="48eab-118">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
