---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 30084143949d2243fd310448c52e6b861505ad66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191252"
---
# <a name="getcustomui"></a>GetCustomUI
구현 하는 경우 호스트에서 사용자 지정 진행률 및 오류 메시지를 가져오려는 PresentationHost.exe에서 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwzProgressAssemblyName`  
  
 [out] 호스트 제공 진행률 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.  
  
 `pwzProgressClassName`  
  
 [out] 가급적 호스트 제공 진행률 사용자 인터페이스는 클래스의 이름을 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 파일을 <xref:System.Windows.Controls.Page> 최상위 요소입니다. 이 클래스가 지정 된 어셈블리에 있는 `pwzProgressAssemblyName`합니다.  
  
 `pwzErrorAssemblyName`  
  
 [out] 호스트 제공 오류 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.  
  
 `pwzErrorClassName`  
  
 [out] 호스트 제공 오류 사용자 클래스의 이름을 인터페이스를 가급적 사용 하 여 XAML 파일 <xref:System.Windows.Controls.Page> 최상위 요소입니다. 이 클래스가 지정 된 어셈블리에 있는 `pwzErrorAssemblyName`합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT: 무시됩니다.  
  
## <a name="remarks"></a>설명  
 호스트 응용 프로그램을 PresentationHost.exe의 기본 사용자 인터페이스를 준수 하지 않는 하는 특정 테마에 있을 수 있습니다. 이 경우 호스트 응용 프로그램 구현할 수 있습니다 [GetCustomUI](getcustomui.md) 를 PresentationHost.exe에 진행률 및 오류 사용자 인터페이스를 반환 합니다. PresentationHost.exe가 항상 호출 [GetCustomUI](getcustomui.md) 해당 기본 사용자 인터페이스를 사용 하기 전에 합니다.  
  
 이 함수는 PresentationHost의 초기화 중에 한 번 호출 됩니다.  
  
## <a name="see-also"></a>참고자료

- [IWpfHostSupport](iwpfhostsupport.md)
