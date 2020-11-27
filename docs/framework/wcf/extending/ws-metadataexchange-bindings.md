---
title: WS-MetadataExchange 바인딩
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293990"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="8f967-102">WS-MetadataExchange 바인딩</span><span class="sxs-lookup"><span data-stu-id="8f967-102">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="8f967-103">이 항목에서는 여러 가지 전송에 대해 기본 메타데이터 교환 바인딩을 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8f967-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="8f967-104">기본 바인딩</span><span class="sxs-lookup"><span data-stu-id="8f967-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="8f967-105">기본 바인딩 이름</span><span class="sxs-lookup"><span data-stu-id="8f967-105">Default Binding Name</span></span>|<span data-ttu-id="8f967-106">바인딩 생성 방법</span><span class="sxs-lookup"><span data-stu-id="8f967-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="8f967-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8f967-107">mexHttpBinding</span></span>|<span data-ttu-id="8f967-108">전송 수준 보안이 비활성화된 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="8f967-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="8f967-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="8f967-109">mexHttpsBinding</span></span>|<span data-ttu-id="8f967-110">전송 수준 보안을 지원하는 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="8f967-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="8f967-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="8f967-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="8f967-112">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 있는 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="8f967-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="8f967-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="8f967-113">mexTcpBinding</span></span>|<span data-ttu-id="8f967-114">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="8f967-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
