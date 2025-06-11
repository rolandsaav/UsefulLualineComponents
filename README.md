# UsefulLualineComponents
Useful Lualine Components I use

Right now there are two LuaLine Components in this plugin:

localMarks: 
This components tells you what local marks are set. 
You can configure what the prefix is, what marks it tracks, and what the delimiter is.

globalMarks:
This components tells you what global marks are set. 
You can configure what the prefix is, what marks it tracks, and what the delimiter is.



# Usage 
```lua 
return { 
	{
		"rolandsaav/UsefulLualineComponents"
	},
	{
	'nvim-lualine/lualine.nvim',
	dependencies = { 'nvim-tree/nvim-web-devicons' },
	config = function()
		local testComponent = require("saav-useful")

		require('lualine').setup {
			sections = {
				lualine_a = { 'mode' },
				lualine_b = { 'branch', 'diff', 'diagnostics' },
				lualine_c = { 'filename' },
				lualine_x = {
					testComponent.localMarks({ letters = "abcd", delimiter = "^" }),
					testComponent.globalMarks({ letters = "ABCD", prefix = "Global Marks:" })
				},
				lualine_y = { 'tabs' },
				lualine_z = { 'location' }
			},
		}
	end
} 
}
```
More documentation coming... maybe

## Todo 
- [ ] add screenshots
- [ ] document configuration stuff 
- [ ] make sure strings are stripped
- [ ] type hints for lsp 
- [ ] rename plugin lol
