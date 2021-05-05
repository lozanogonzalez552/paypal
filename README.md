
export type ModelEffect<
	TModels extends Models<TModels> = Record<string, any>
> = (
	payload: Action['payload'],
	rootState: RematchRootState<TModels>,
	meta: Action['meta']
) => any
Is the current type for an effect, you will see that if you add the this property with anything else, you get autocomplete of the rootstate:

export type ModelEffect<
	TModels extends Models<TModels> = Record<string, any>
> = (
    this: RematchRootState<TModels>
	payload: Action['payload'],
	rootState: RematchRootState<TModels>,
	meta: Action['meta']
) => any
We must add ExtractReducers&Effects<TModel> 
