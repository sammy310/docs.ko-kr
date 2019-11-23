---
title: Wcf 개발자를 위한 gRPC gRPC로 WCF 솔루션 마이그레이션
description: 다양 한 형식의 WCF 서비스를 gRPC의 해당 항목으로 마이그레이션하는 방법입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 33823d20e1593323a03da12981c5a4534c4d491a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971765"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="f644d-103">GRPC로 WCF 솔루션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f644d-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="f644d-104">이 장에서는 ASP.NET Core 3.0 gRPC 프로젝트를 사용 하는 방법을 살펴보고 다양 한 유형의 WCF 서비스를 gRPC로 마이그레이션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-104">This chapter will look at how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of WCF service to the gRPC equivalent:</span></span>

- <span data-ttu-id="f644d-105">ASP.NET Core 3.0 gRPC 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="f644d-106">단순 요청-gRPC 단항 RPC에 대 한 응답 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-106">Simple Request-Reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="f644d-107">단일 방식으로 Pc 클라이언트 스트리밍 RPC를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="f644d-108">전체 이중 서비스와 gRPC 양방향 스트리밍 RPC.</span><span class="sxs-lookup"><span data-stu-id="f644d-108">Full Duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="f644d-109">스트리밍 서비스와 데이터 집합을 반환 하는 데 반복 되는 필드를 사용 하는 것과 챕터의 끝에 클라이언트 라이브러리를 사용 하는 것도 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-109">There's also a comparison of using streaming services versus repeated fields for returning data sets, and the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="f644d-110">샘플 WCF 응용 프로그램은 종속성 주입을 위해 *Autofac* 라는 오픈 소스 IoC (제어의 반전) 컨테이너 라이브러리를 사용 하 여 주식 거래 서비스 집합의 최소 스텁입니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-110">The sample WCF application is a minimal stub of a set of stock trading services, using the open-source Inversion of Control (IoC) container library called *Autofac* for dependency injection.</span></span> <span data-ttu-id="f644d-111">각 WCF 서비스 유형에 대해 하나씩 세 개의 서비스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-111">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="f644d-112">이 서비스는 다음 섹션에서 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-112">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="f644d-113">솔루션은 GitHub의 [dotnet-architecture/grpc-wcf 개발자](https://github.com/dotnet-architecture/grpc-for-wcf-developers) 에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-113">The solutions can be downloaded from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="f644d-114">서비스는 가짜 데이터를 사용 하 여 외부 종속성을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-114">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="f644d-115">샘플에는 각 서비스의 WCF 및 gRPC 구현이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f644d-115">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f644d-116">[이전](ws-protocols.md)
>[다음](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="f644d-116">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
