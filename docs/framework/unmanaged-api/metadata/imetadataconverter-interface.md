---
title: "IMetaDataConverter 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter
helpviewer_keywords: IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f551a774a860f595cc90a7cca9eee2c726ef50ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="6824d-102">IMetaDataConverter 介面</span><span class="sxs-lookup"><span data-stu-id="6824d-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="6824d-103">提供將類型程式庫對應至它們的中繼資料簽章，以及從一個轉換到另一個的方法。</span><span class="sxs-lookup"><span data-stu-id="6824d-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6824d-104">方法</span><span class="sxs-lookup"><span data-stu-id="6824d-104">Methods</span></span>  
  
|<span data-ttu-id="6824d-105">方法</span><span class="sxs-lookup"><span data-stu-id="6824d-105">Method</span></span>|<span data-ttu-id="6824d-106">說明</span><span class="sxs-lookup"><span data-stu-id="6824d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6824d-107">GetMetaDataFromTypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="6824d-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="6824d-108">取得指標[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)執行個體，表示指定所參考的類型程式庫的中繼資料簽章`ITypeInfo`執行個體。</span><span class="sxs-lookup"><span data-stu-id="6824d-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="6824d-109">GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="6824d-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="6824d-110">取得指標`IMetaDataImport`執行個體，表示由指定的類型程式庫的中繼資料簽章`ITypeLib`執行個體。</span><span class="sxs-lookup"><span data-stu-id="6824d-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="6824d-111">GetTypeLibFromMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="6824d-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="6824d-112">取得指標`ITypeLib`代表有指定的模組和程式庫名稱的類型程式庫的執行個體。</span><span class="sxs-lookup"><span data-stu-id="6824d-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6824d-113">需求</span><span class="sxs-lookup"><span data-stu-id="6824d-113">Requirements</span></span>  
 <span data-ttu-id="6824d-114">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6824d-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6824d-115">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6824d-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6824d-116">**程式庫：**做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="6824d-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6824d-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6824d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6824d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6824d-118">See Also</span></span>  
 [<span data-ttu-id="6824d-119">中繼資料介面</span><span class="sxs-lookup"><span data-stu-id="6824d-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="6824d-120">IMetaDataImport 介面</span><span class="sxs-lookup"><span data-stu-id="6824d-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)