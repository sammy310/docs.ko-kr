---
title: ASP.NET에서 System.Transactions 사용
description: ASP.NET 응용 프로그램 내부에서 시스템 트랜잭션을 사용 합니다. 분산 트랜잭션 권한을 사용 하도록 설정 하 고 동적 컴파일을 사용 합니다.
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: b6663e9258e98e94d7b739ee75c826ced1e2f897
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186720"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="c6b2c-104">ASP.NET에서 System.Transactions 사용</span><span class="sxs-lookup"><span data-stu-id="c6b2c-104">Using System.Transactions in ASP.NET</span></span>

<span data-ttu-id="c6b2c-105">이 항목에서는 ASP.NET 응용 프로그램 내부에서 <xref:System.Transactions>를 성공적으로 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-105">This topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>

## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="c6b2c-106">ASP.NET에서 DistributedTransactionPermission 사용</span><span class="sxs-lookup"><span data-stu-id="c6b2c-106">Enable DistributedTransactionPermission in ASP.NET</span></span>

 <span data-ttu-id="c6b2c-107"><xref:System.Transactions> 는 부분적으로 신뢰할 수 있는 호출자를 지원 하며 `AllowPartiallyTrustedCallers` 특성 (APTCA)으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-107"><xref:System.Transactions> supports partially trusted callers and is marked with the `AllowPartiallyTrustedCallers` attribute (APTCA).</span></span> <span data-ttu-id="c6b2c-108">에 대 한 신뢰 수준은 <xref:System.Transactions> 가 노출 하는 리소스 유형 (예: 시스템 메모리, 공유 프로세스 전체 리소스, 시스템 차원 리소스 및 기타 리소스)을 기반으로 정의 되며, <xref:System.Transactions> 이러한 리소스에 액세스 하는 데 필요한 신뢰 수준을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-108">The trust levels for <xref:System.Transactions> are defined based on the types of resources (for example, system memory, shared process-wide resources, system-wide resources, and other resources) that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="c6b2c-109">부분 신뢰 환경에서 완전 신뢰가 아닌 어셈블리는 <xref:System.Transactions.DistributedTransactionPermission>이 부여되지 않은 경우 애플리케이션 도메인 내에서만 트랜잭션을 사용할 수 있습니다(이 경우 보호되는 리소스는 시스템 메모리뿐임).</span><span class="sxs-lookup"><span data-stu-id="c6b2c-109">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>

 <span data-ttu-id="c6b2c-110">MSDTC(Microsoft Distributed Transaction Coordinator)에서 관리하도록 트랜잭션 관리를 에스컬레이션할 때마다<xref:System.Transactions.DistributedTransactionPermission> 이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-110"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="c6b2c-111">이 종류의 시나리오에서는 프로세스 범위 리소스, 특히 MSDTC 로그의 예약된 공간인 전역 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-111">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="c6b2c-112">이러한 사용 예로 데이터베이스에 대한 웹 프런트 엔드 또는 제공하는 서비스의 일부로 데이터베이스를 사용하는 애플리케이션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-112">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>

 <span data-ttu-id="c6b2c-113">ASP.NET에는 자체 신뢰 수준이 있으며 정책 파일을 통해 특정 사용 권한 집합을 이러한 신뢰 수준과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-113">ASP.NET has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="c6b2c-114">자세한 내용은 [ASP.NET Trust Levels And Policy Files](/previous-versions/aspnet/wyts434y(v=vs.100))항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-114">For more information, see [ASP.NET Trust Levels and Policy Files](/previous-versions/aspnet/wyts434y(v=vs.100)).</span></span> <span data-ttu-id="c6b2c-115">Windows SDK를 처음 설치 하는 경우 기본 ASP.NET 정책 파일이와 연결 되지 않습니다 <xref:System.Transactions.DistributedTransactionPermission> .</span><span class="sxs-lookup"><span data-stu-id="c6b2c-115">When you initially install the Windows SDK, none of the default ASP.NET policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="c6b2c-116">따라서 MSDTC에서 관리하도록 ASP.NET 응용 프로그램의 트랜잭션을 에스컬레이션하는 경우 <xref:System.Security.SecurityException>을 요청할 때 <xref:System.Transactions.DistributedTransactionPermission>이 발생하며 에스컬레이션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-116">As such, when your transaction in an ASP.NET application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="c6b2c-117">ASP.NET 부분 신뢰 환경에서 트랜잭션 에스컬레이션을 사용하려면 <xref:System.Transactions.DistributedTransactionPermission>과 동일한 기본 신뢰 수준에서 <xref:System.Data.SqlClient.SqlClientPermission>을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-117">To enable transaction escalation in an ASP.NET partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="c6b2c-118">이를 지원하도록 사용자 지정 신뢰 수준과 정책 파일을 구성하거나 **Web_hightrust.config** 및 **Web_mediumtrust.config**인 기본 정책 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-118">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>

 <span data-ttu-id="c6b2c-119">정책 파일을 수정 하려면 요소 아래의 요소에 요소를 추가 하 `SecurityClass` `DistributedTransactionPermission` `SecurityClasses` `PolicyLevel` 고 `IPermission` ASP.NET `NamedPermissionSet` 에 대해 해당 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-119">To modify the policy files, add a `SecurityClass` element for `DistributedTransactionPermission` to the `SecurityClasses` element under the `PolicyLevel` element and add a corresponding `IPermission` element under the ASP.NET `NamedPermissionSet` for System.Transactions.</span></span> <span data-ttu-id="c6b2c-120">다음 구성 파일에서 이 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-120">The following configuration file demonstrates this.</span></span>

```xml
<SecurityClasses>
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
...
</SecurityClasses>

<PermissionSet
  class="NamedPermissionSet"
  version="1"
  Name="ASP.Net">
     <IPermission
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
        version="1"
        Unrestricted="true"
     />
...
</PermissionSet>
```

 <span data-ttu-id="c6b2c-121">ASP.NET 보안 정책에 대 한 자세한 내용은 [Ws-securitypolicy 요소 (ASP.NET Settings 스키마)](/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-121">For more information about ASP.NET security policy, see [securityPolicy Element (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span></span>

## <a name="dynamic-compilation"></a><span data-ttu-id="c6b2c-122">동적 컴파일</span><span class="sxs-lookup"><span data-stu-id="c6b2c-122">Dynamic Compilation</span></span>

 <span data-ttu-id="c6b2c-123">액세스 시 동적으로 컴파일되는 ASP.NET 환경에서 <xref:System.Transactions>를 가져오고 사용하려면 <xref:System.Transactions> 어셈블리에 대한 참조를 구성 파일에 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-123">If you want to import and use <xref:System.Transactions> in an ASP.NET application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="c6b2c-124">특히 `compilation/assemblies` 기본 루트 **Web.config** 구성 파일 또는 특정 웹 응용 프로그램의 구성 파일의 섹션 아래에 참조를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-124">Specifically, the reference should be added under the `compilation/assemblies` section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="c6b2c-125">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-125">The following example demonstrates this.</span></span>

```xml
<configuration>
   <system.web>
      <compilation>
         <assemblies>
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
         </assemblies>
      </compilation>
   </system.web>
</configuration>
```

 <span data-ttu-id="c6b2c-126">자세한 내용은 [컴파일의 요소에 대 한 Add 요소 (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6b2c-126">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6b2c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6b2c-127">See also</span></span>

- <span data-ttu-id="c6b2c-128">[ASP.NET Trust Levels and Policy Files](/previous-versions/aspnet/wyts434y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c6b2c-128">[ASP.NET Trust Levels and Policy Files](/previous-versions/aspnet/wyts434y(v=vs.100))</span></span>
- <span data-ttu-id="c6b2c-129">[securityPolicy 요소(ASP.NET 설정 스키마)](/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c6b2c-129">[securityPolicy Element (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span></span>
- [<span data-ttu-id="c6b2c-130">트랜잭션 관리 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="c6b2c-130">Transaction Management Escalation</span></span>](transaction-management-escalation.md)
