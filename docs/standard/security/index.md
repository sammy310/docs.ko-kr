---
title: .NET의 보안
description: .NET의 보안에 대해 알아봅니다. 주요 보안 개념, 역할 기반 보안, 암호화 모델 및 보안 코딩 지침에 대해 설명 하는 링크를 따르세요.
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
ms.openlocfilehash: 21511b580a4f922d2aef04cc79f5d551f0406b45
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767821"
---
# <a name="security-in-net"></a><span data-ttu-id="6af39-104">.NET의 보안</span><span class="sxs-lookup"><span data-stu-id="6af39-104">Security in .NET</span></span>

<span data-ttu-id="6af39-105">공용 언어 런타임 및 .NET은 개발자가 보안 코드를 쉽게 작성 하 고 시스템 관리자가 보호 된 리소스에 액세스할 수 있도록 코드에 부여 된 권한을 사용자 지정할 수 있게 해 주는 많은 유용한 클래스 및 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-105">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="6af39-106">또한 런타임 및 .NET은 암호화 및 역할 기반 보안을 사용 하는 데 도움이 되는 유용한 클래스 및 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-106">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6af39-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="6af39-107">In this section</span></span>

- [<span data-ttu-id="6af39-108">주요 보안 개념</span><span class="sxs-lookup"><span data-stu-id="6af39-108">Key Security Concepts</span></span>](key-security-concepts.md)  
<span data-ttu-id="6af39-109">공용 언어 런타임 보안 기능에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="6af39-110">이 섹션은 개발자와 시스템 관리자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-110">This section is of interest to developers and system administrators.</span></span>

- [<span data-ttu-id="6af39-111">역할 기반 보안</span><span class="sxs-lookup"><span data-stu-id="6af39-111">Role-Based Security</span></span>](role-based-security.md)  
<span data-ttu-id="6af39-112">코드에서 역할 기반 보안과 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="6af39-113">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-113">This section is of interest to developers.</span></span>

- [<span data-ttu-id="6af39-114">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="6af39-114">Cryptography Model</span></span>](cryptography-model.md)  
<span data-ttu-id="6af39-115">.NET에서 제공 하는 암호화 서비스에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-115">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="6af39-116">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-116">This section is of interest to developers.</span></span>

- [<span data-ttu-id="6af39-117">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="6af39-117">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)  
<span data-ttu-id="6af39-118">안정적인 .NET 응용 프로그램을 만들기 위한 몇 가지 모범 사례를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-118">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="6af39-119">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-119">This section is of interest to developers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6af39-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6af39-120">Related sections</span></span>

[<span data-ttu-id="6af39-121">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="6af39-121">Development Guide</span></span>](../../framework/development-guide.md)  
<span data-ttu-id="6af39-122">만들기, 구성, 디버깅, 보안, 애플리케이션 배포, 동적 프로그래밍에 대한 정보, 상호 운용성, 확장성, 메모리 관리 및 스레딩을 포함하여 애플리케이션 개발에 대한 모든 주요 기술 분야 및 작업에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6af39-122">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
