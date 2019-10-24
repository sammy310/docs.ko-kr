---
title: .NET의 보안
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c3c7eb20bb3368205dab4c7e03b6b80d09a2121
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775267"
---
# <a name="security-in-net"></a><span data-ttu-id="e8f51-102">.NET의 보안</span><span class="sxs-lookup"><span data-stu-id="e8f51-102">Security in .NET</span></span>

<span data-ttu-id="e8f51-103">공용 언어 런타임 및 .NET은 개발자가 보안 코드를 쉽게 작성 하 고 시스템 관리자가 보호 된 리소스에 액세스할 수 있도록 코드에 부여 된 권한을 사용자 지정할 수 있게 해 주는 많은 유용한 클래스 및 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-103">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="e8f51-104">또한 런타임 및 .NET은 암호화 및 역할 기반 보안을 사용 하는 데 도움이 되는 유용한 클래스 및 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-104">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e8f51-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e8f51-105">In this section</span></span>

- [<span data-ttu-id="e8f51-106">주요 보안 개념</span><span class="sxs-lookup"><span data-stu-id="e8f51-106">Key Security Concepts</span></span>](key-security-concepts.md)  
<span data-ttu-id="e8f51-107">공용 언어 런타임 보안 기능에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-107">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="e8f51-108">이 섹션은 개발자와 시스템 관리자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-108">This section is of interest to developers and system administrators.</span></span>

- [<span data-ttu-id="e8f51-109">역할 기반 보안</span><span class="sxs-lookup"><span data-stu-id="e8f51-109">Role-Based Security</span></span>](role-based-security.md)  
<span data-ttu-id="e8f51-110">코드에서 역할 기반 보안과 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-110">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="e8f51-111">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-111">This section is of interest to developers.</span></span>

- [<span data-ttu-id="e8f51-112">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="e8f51-112">Cryptography Model</span></span>](cryptography-model.md)  
<span data-ttu-id="e8f51-113">.NET에서 제공 하는 암호화 서비스에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-113">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="e8f51-114">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-114">This section is of interest to developers.</span></span>

- [<span data-ttu-id="e8f51-115">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="e8f51-115">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)  
<span data-ttu-id="e8f51-116">안정적인 .NET 응용 프로그램을 만들기 위한 몇 가지 모범 사례를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-116">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="e8f51-117">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-117">This section is of interest to developers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="e8f51-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e8f51-118">Related sections</span></span>

[<span data-ttu-id="e8f51-119">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="e8f51-119">Development Guide</span></span>](../../framework/development-guide.md)  
<span data-ttu-id="e8f51-120">만들기, 구성, 디버깅, 보안, 애플리케이션 배포, 동적 프로그래밍에 대한 정보, 상호 운용성, 확장성, 메모리 관리 및 스레딩을 포함하여 애플리케이션 개발에 대한 모든 주요 기술 분야 및 작업에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f51-120">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
