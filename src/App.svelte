<script>
    import marked from 'marked';
    let source = `
# H1 heading

## H2 heading

### H3 heading

---

**bold text**

*italicized text*

---

1. First item
2. Second item
3. Third item

- First item
- Second item
- Third item

[Svelte](https://svelte.dev/)
`;
    let markdown = marked(source);
</script>
<main class="container">
<header class="header">
    <h1 class="header-title">Svelte markdown editor</h1>
</header>

<div class="markdown-editor">
    <div class="left-panel">
        <textarea bind:value={source} class="source"></textarea>
    </div>

    <div class="right-panel">
        <div class="output">{@html markdown}</div>
    </div>
</div>
</main>

<style>
	.container{
		background: #ff3e00d6;
		padding:10px 30px;
	}
    .header {
        height: 10vh;
        display: flex;
        align-items: center;
        justify-content: center;
		
    }
    .header-title {
        margin: 0;
		color:#fff;
    }
    .markdown-editor {
        width: 100%;
        display: flex;
        align-items:flex-start;
        justify-content: space-evenly;
    }
    .left-panel, .right-panel {
        width: 50%;
        border: solid 1px black;
        height: 85vh;
		background: #ffffff;
    }
    .right-panel {
        overflow: auto;
    }
    .source {
        border: none;
        width: 100%;
        height: 100%;
		background: #001628;
		color: #83ba52;
    }
    .source:focus {
        outline: none;
    }
    .output {
        width: 100%;
        padding: 0 2em;
    }

</style>