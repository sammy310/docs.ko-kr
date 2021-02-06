---
description: '다음에 대 한 자세한 정보: 바인딩 WS-MetadataExchange'
title: WS-MetadataExchange 바인딩
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 3bcea573ad436a85285fab5657e58defa9113d9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643945"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="ef2d2-103">WS-MetadataExchange 바인딩</span><span class="sxs-lookup"><span data-stu-id="ef2d2-103">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="ef2d2-104">이 항목에서는 여러 가지 전송에 대해 기본 메타데이터 교환 바인딩을 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-104">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="ef2d2-105">기본 바인딩</span><span class="sxs-lookup"><span data-stu-id="ef2d2-105">The Default Bindings</span></span>  
  
|<span data-ttu-id="ef2d2-106">기본 바인딩 이름</span><span class="sxs-lookup"><span data-stu-id="ef2d2-106">Default Binding Name</span></span>|<span data-ttu-id="ef2d2-107">바인딩 생성 방법</span><span class="sxs-lookup"><span data-stu-id="ef2d2-107">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="ef2d2-108">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ef2d2-108">mexHttpBinding</span></span>|<span data-ttu-id="ef2d2-109">전송 수준 보안이 비활성화된 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-109">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="ef2d2-110">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="ef2d2-110">mexHttpsBinding</span></span>|<span data-ttu-id="ef2d2-111">전송 수준 보안을 지원하는 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-111">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="ef2d2-112">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="ef2d2-112">mexNamedPipeBinding</span></span>|<span data-ttu-id="ef2d2-113">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 있는 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-113">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="ef2d2-114">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="ef2d2-114">mexTcpBinding</span></span>|<span data-ttu-id="ef2d2-115">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2d2-115">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
