<script>
  import { getContext } from "svelte"
  export let imageUrl
  export let NoimageUrl = 'data:image/png;base64,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'
  export let size
  export let color = 'black'
  export let title
  export let department
  export let name 
  export let isShowingDetails

if(!imageUrl) {
  imageUrl = NoimageUrl
}

  const { styleable } = getContext("sdk")
  const component = getContext("component")
</script>

<div use:styleable={$component.styles}>
  <div class="container">
    <div style="flex: 0 0 auto;">
      <img src="{imageUrl}" alt="avatar" class="image-class" style="--size:{size};"/>
    </div>
    {#if isShowingDetails}
    <div class="text-container" style="--color:{color};">
      <span>{name}</span>
      <p class="department">{department}</p>
      <p class="title">{title}</p>
    </div>
    {/if}
  </div>
</div>

<style>
.container {
  display: flex;
  align-items: center;
}
.image-class {
  border-radius: 50%;
  height: var(--size, 32px);
  width: var(--size, 32px);
  object-fit: cover;
  overflow: hidden;
}
.text-container {
  color: var(--color, black);
  font-size: 12px;
  font-weight: 600;
  line-height: 16px;
  overflow-wrap: break-word;
  margin-left: 8px;
  overflow: hidden;
  text-overflow: ellipsis;  
  white-space: nowrap;
}
.department {
  font-weight: 400;
}
.title {
  font-weight: 300;
}
</style>