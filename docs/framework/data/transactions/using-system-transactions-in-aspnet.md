---
title: ASP.NET에서 System.Transactions 사용
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 2bddebc13897408839e18f42b17a9fbaefdc5b87
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040417"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="2d037-102">ASP.NET에서 System.Transactions 사용</span><span class="sxs-lookup"><span data-stu-id="2d037-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="2d037-103">이 항목에서는 ASP.NET 응용 프로그램 내부에서 <xref:System.Transactions>를 성공적으로 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-103">This topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>

## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="2d037-104">ASP.NET에서 DistributedTransactionPermission 사용</span><span class="sxs-lookup"><span data-stu-id="2d037-104">Enable DistributedTransactionPermission in ASP.NET</span></span>
 <span data-ttu-id="2d037-105"><xref:System.Transactions>는 부분적으로 신뢰할 수 있는 호출자를 지원하며 `AllowPartiallyTrustedCallers` 특성(APTCA)으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-105"><xref:System.Transactions> supports partially trusted callers and is marked with the `AllowPartiallyTrustedCallers` attribute (APTCA).</span></span> <span data-ttu-id="2d037-106"><xref:System.Transactions>에 대 한 신뢰 수준은 표시 <xref:System.Transactions>는 리소스의 유형 (예: 시스템 메모리, 공유 프로세스 차원의 리소스, 시스템 차원 리소스 및 기타 리소스)에 따라 정의 되며, 이러한 리소스에 액세스 하는 데 필요한 신뢰 수준이 제공 됩니다. 인사.</span><span class="sxs-lookup"><span data-stu-id="2d037-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources (for example, system memory, shared process-wide resources, system-wide resources, and other resources) that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="2d037-107">부분 신뢰 환경에서 완전 신뢰가 아닌 어셈블리는 <xref:System.Transactions.DistributedTransactionPermission>이 부여되지 않은 경우 애플리케이션 도메인 내에서만 트랜잭션을 사용할 수 있습니다(이 경우 보호되는 리소스는 시스템 메모리뿐임).</span><span class="sxs-lookup"><span data-stu-id="2d037-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>

 <span data-ttu-id="2d037-108">MSDTC(Microsoft Distributed Transaction Coordinator)에서 관리하도록 트랜잭션 관리를 에스컬레이션할 때마다<xref:System.Transactions.DistributedTransactionPermission> 이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="2d037-109">이 종류의 시나리오에서는 프로세스 범위 리소스, 특히 MSDTC 로그의 예약된 공간인 전역 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="2d037-110">이러한 사용 예로 데이터베이스에 대한 웹 프런트 엔드 또는 제공하는 서비스의 일부로 데이터베이스를 사용하는 애플리케이션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>

 <span data-ttu-id="2d037-111">ASP.NET에는 자체 신뢰 수준이 있으며 정책 파일을 통해 특정 사용 권한 집합을 이러한 신뢰 수준과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-111">ASP.NET has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="2d037-112">자세한 내용은 [ASP.NET Trust Levels And Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d037-112">For more information, see [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span></span> <span data-ttu-id="2d037-113">Windows SDK를 처음 설치 하는 경우에는 <xref:System.Transactions.DistributedTransactionPermission>에 연결 된 기본 ASP.NET 정책 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-113">When you initially install the Windows SDK, none of the default ASP.NET policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="2d037-114">따라서 MSDTC에서 관리하도록 ASP.NET 응용 프로그램의 트랜잭션을 에스컬레이션하는 경우 <xref:System.Security.SecurityException>을 요청할 때 <xref:System.Transactions.DistributedTransactionPermission>이 발생하며 에스컬레이션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-114">As such, when your transaction in an ASP.NET application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="2d037-115">ASP.NET 부분 신뢰 환경에서 트랜잭션 에스컬레이션을 사용하려면 <xref:System.Transactions.DistributedTransactionPermission>과 동일한 기본 신뢰 수준에서 <xref:System.Data.SqlClient.SqlClientPermission>을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-115">To enable transaction escalation in an ASP.NET partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="2d037-116">이를 지원하도록 사용자 지정 신뢰 수준과 정책 파일을 구성하거나 **Web_hightrust.config** 및 **Web_mediumtrust.config**인 기본 정책 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>

 <span data-ttu-id="2d037-117">정책 파일을 수정하려면 `SecurityClass`에 대한 `DistributedTransactionPermission` 요소를 `SecurityClasses` 요소의 `PolicyLevel` 요소 아래에 추가하고 해당 `IPermission` 요소를 System.Transactions에 대한 ASP.NET `NamedPermissionSet` 아래에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-117">To modify the policy files, add a `SecurityClass` element for `DistributedTransactionPermission` to the `SecurityClasses` element under the `PolicyLevel` element and add a corresponding `IPermission` element under the ASP.NET `NamedPermissionSet` for System.Transactions.</span></span> <span data-ttu-id="2d037-118">다음 구성 파일에서 이 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-118">The following configuration file demonstrates this.</span></span>

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

 <span data-ttu-id="2d037-119">ASP.NET 보안 정책에 대 한 자세한 내용은 [Ws-securitypolicy 요소 (ASP.NET Settings 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d037-119">For more information about ASP.NET security policy, see [securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span></span>

## <a name="dynamic-compilation"></a><span data-ttu-id="2d037-120">동적 컴파일</span><span class="sxs-lookup"><span data-stu-id="2d037-120">Dynamic Compilation</span></span>
 <span data-ttu-id="2d037-121">액세스 시 동적으로 컴파일되는 ASP.NET 환경에서 <xref:System.Transactions>를 가져오고 사용하려면 <xref:System.Transactions> 어셈블리에 대한 참조를 구성 파일에 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-121">If you want to import and use <xref:System.Transactions> in an ASP.NET application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="2d037-122">특히 **기본 루트 web.config** 구성 파일의 `compilation/assemblies` 섹션 또는 특정 웹 응용 프로그램의 구성 파일에 참조를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-122">Specifically, the reference should be added under the `compilation/assemblies` section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="2d037-123">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2d037-123">The following example demonstrates this.</span></span>

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

 <span data-ttu-id="2d037-124">자세한 내용은 [컴파일의 요소에 대 한 Add 요소 (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d037-124">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="2d037-125">참조</span><span class="sxs-lookup"><span data-stu-id="2d037-125">See also</span></span>

- <span data-ttu-id="2d037-126">[ASP.NET 신뢰 수준 및 정책 파일](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2d037-126">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span></span>
- <span data-ttu-id="2d037-127">[Ws-securitypolicy 요소 (ASP.NET Settings 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2d037-127">[securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span></span>
- [<span data-ttu-id="2d037-128">트랜잭션 관리 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="2d037-128">Transaction Management Escalation</span></span>](transaction-management-escalation.md)
